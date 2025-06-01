project(
    'libswiftdemangle',
    ['cpp', 'c'],
    version: '0.1.0',
    meson_version: '>= 0.62.0',
    default_options: [
        'werror=false',
        'cpp_std=gnu++17',
    ],
)
pkg = import('pkgconfig')

inc = include_directories(
    'include',
    'include/demangling',
    'include/stdlib/public/runtime',
)
include_dir = include_directories('include')

llvm_dep = dependency('llvm')

subdir('src')
subdir('tests')

install_headers(files('include/swiftdemangle.h'))
