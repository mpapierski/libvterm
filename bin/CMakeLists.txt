add_executable (unterm
    unterm.c
    )
target_link_libraries (unterm
    vterm
    )

add_executable (vterm-ctrl
    vterm-ctrl.c
    )
target_link_libraries (vterm-ctrl
    vterm
    )

add_executable (vterm-dump
    vterm-dump.c
    )
target_link_libraries (vterm-dump
    vterm
    )