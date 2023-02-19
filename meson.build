project(
    'nyagetty',
    ['c', 'cpp'],
    version: '2.38.99',
    # i'd use warning_level=3 but it does not like the %m format
    default_options: ['c_std=gnu99', 'warning_level=2'],
    license: '0BSD',
)

add_project_arguments('-D_PATH_RUNSTATEDIR="/run"', language: 'c')
add_project_arguments(
    '-D_PATH_SYSCONFSTATICDIR="' + join_paths(get_option('prefix'), get_option('libdir')) + '"',
    language: 'c'
)

executable(
    'agetty', ['agetty.c'],
    install: true,
)

