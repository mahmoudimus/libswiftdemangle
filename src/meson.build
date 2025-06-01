swiftdemangler_sources = [
    'Context.cpp',
    'Demangle.cpp',
    'Demangler.cpp',
    'Errors.cpp',
    'ManglingUtils.cpp',
    'NodeDumper.cpp',
    'NodePrinter.cpp',
    'OldDemangler.cpp',
    'OldRemangler.cpp',
    'Portability.cpp',
    'Punycode.cpp',
    'Remangler.cpp',
]

swift_demangler_defines = [
    '-DLLVM_DISABLE_ABI_BREAKING_CHECKS_ENFORCING=1',
    '-DSWIFT_SUPPORT_OLD_MANGLING=1',
    '-DSWIFT_STDLIB_HAS_TYPE_PRINTING=1',
    '-Wno-unused-variable',
    '-Wno-unknown-pragmas',
    '-Wno-invalid-offsetof',
    '-Ulinux',
]

swift_demangler_deps = [llvm_dep]

swift_demangler_lib = static_library(
    'swiftdemangler',
    swiftdemangler_sources,
    dependencies: swift_demangler_deps,
    include_directories: inc,
    install: true,
    cpp_args: swift_demangler_defines,
)

# Define the shared library
swift_demangler_shared = shared_library(
    'swiftdemangler',
    swiftdemangler_sources,
    dependencies: swift_demangler_deps,
    include_directories: inc,
    install: true,
    cpp_args: swift_demangler_defines,
)

swift_demangler_dep = declare_dependency(
    include_directories: include_dir,
    link_with: swift_demangler_lib,
    dependencies: swift_demangler_deps,
)

pkg.generate(swift_demangler_lib)
