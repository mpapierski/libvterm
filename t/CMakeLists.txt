add_executable (harness
    harness.c
    )
target_link_libraries (harness
    vterm
    )

add_test (NAME 02parser
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 02parser.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 03encoding_utf8
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 03encoding_utf8.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 10state_putglyph
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 10state_putglyph.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 11state_movecursor
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 11state_movecursor.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 12state_scroll
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 12state_scroll.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 13state_edit
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 13state_edit.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 14state_encoding
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 14state_encoding.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 15state_mode
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 15state_mode.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 16state_resize
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 16state_resize.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 17state_mouse
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 17state_mouse.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 18state_termprops
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 18state_termprops.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 20state_wrapping
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 20state_wrapping.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 21state_tabstops
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 21state_tabstops.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 22state_save
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 22state_save.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 25state_input
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 25state_input.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 26state_query
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 26state_query.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 27state_reset
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 27state_reset.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 28state_dbl_wh
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 28state_dbl_wh.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 29state_fallback
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 29state_fallback.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 30pen
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 30pen.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 40screen_ascii
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 40screen_ascii.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 41screen_unicode
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 41screen_unicode.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 42screen_damage
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 42screen_damage.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 43screen_resize
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 43screen_resize.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 44screen_pen
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 44screen_pen.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 45screen_protect
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 45screen_protect.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 46screen_extent
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 46screen_extent.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 47screen_dbl_wh
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 47screen_dbl_wh.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 48screen_termprops
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 48screen_termprops.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_01-movement-1
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_01-movement-1.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_01-movement-2
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_01-movement-2.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_01-movement-3
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_01-movement-3.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_01-movement-4
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_01-movement-4.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_02-screen-1
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_02-screen-1.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_02-screen-2
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_02-screen-2.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_02-screen-3
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_02-screen-3.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
add_test (NAME 90vttest_02-screen-4
    COMMAND ${PERL_EXECUTABLE} run-test.pl --exe $<TARGET_FILE:harness> 90vttest_02-screen-4.test
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})