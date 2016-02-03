cmake_minimum_required (VERSION 2.6)
project (libvterm C)

find_package (Perl REQUIRED)

include_directories (
    include/
    )

add_custom_command (OUTPUT src/encoding/DECdrawing.inc
    COMMAND ${PERL_EXECUTABLE} -CSD tbl2inc_c.pl src/encoding/DECdrawing.tbl > src/encoding/DECdrawing.inc
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    VERBATIM)

add_custom_command (OUTPUT src/encoding/uk.inc
    COMMAND ${PERL_EXECUTABLE} -CSD tbl2inc_c.pl src/encoding/uk.tbl > src/encoding/uk.inc
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
    src/encoding/uk.inc
    src/encoding/DECdrawing.inc
    )
