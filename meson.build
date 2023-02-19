project(
    'nyagetty',
    ['c'],
    version: '2.38.99',
    default_options: ['c_std=gnu99', 'warning_level=3'],
    license: '0BSD',
)

cc = meson.get_compiler('c')

# warning: ISO C does not support the ‘%m’ gnu_printf format
if cc.has_argument('-Wpedantic')
    add_project_arguments('-Wno-pedantic', language: 'c')
endif

add_project_arguments(
    '-DPACKAGE_VERSION="' + meson.project_version() + '"', language: 'c'
)

add_project_arguments('-D_PATH_RUNSTATEDIR="/run"', language: 'c')
add_project_arguments(
    '-D_PATH_SYSCONFSTATICDIR="' + join_paths(
        get_option('prefix'), get_option('libdir')
    ) + '"',
    language: 'c'
)

executable(
    'agetty', ['agetty.c'],
    install: true,
)

install_man('agetty.8')
