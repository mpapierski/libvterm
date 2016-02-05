cmake_minimum_required (VERSION 2.6)
project (libvterm C)

option (LIBVTERM_TESTS "Build libvterm tests" OFF)
option (LIBVTERM_BIN "Build executables" OFF)

find_package (Perl REQUIRED)

include_directories (
    include/
    # Some generated files are located here
    ${CMAKE_CURRENT_BINARY_DIR}
    )

if (CMAKE_BUILD_TYPE STREQUAL "Debug")
    add_definitions (-DDEBUG)
endif ()

set (CMAKE_C_FLAGS "--std=c99")

# We create the output in fake "encoding" directory just to save on patching
# source code.
set (encoding_DIR ${CMAKE_CURRENT_BINARY_DIR}/encoding)

add_custom_command (OUTPUT ${encoding_DIR}/DECdrawing.inc
    COMMAND ${CMAKE_COMMAND} -E make_directory ${encoding_DIR}
    COMMAND ${PERL_EXECUTABLE} -CSD tbl2inc_c.pl src/encoding/DECdrawing.tbl > ${encoding_DIR}/DECdrawing.inc
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    VERBATIM)

add_custom_command (OUTPUT ${encoding_DIR}/uk.inc
    COMMAND ${CMAKE_COMMAND} -E make_directory ${encoding_DIR}
    COMMAND ${PERL_EXECUTABLE} -CSD tbl2inc_c.pl src/encoding/uk.tbl > ${encoding_DIR}/uk.inc
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    VERBATIM)

add_library (vterm
    src/encoding.c
    src/keyboard.c
    src/mouse.c
    src/parser.c
    src/pen.c
    src/screen.c
    src/state.c
    src/unicode.c
    src/vterm.c
    ${encoding_DIR}/DECdrawing.inc
    ${encoding_DIR}/uk.inc
    )

install (TARGETS vterm
    DESTINATION lib)

install (FILES include/vterm.h include/vterm_keycodes.h
    DESTINATION include)

if (LIBVTERM_BIN)
    add_subdirectory (bin)
endif ()

if (LIBVTERM_TESTS)
    enable_testing ()
    add_subdirectory (t)
endif ()
