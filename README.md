# Conan Profile Collection

This repository contains a set of pre-configured Conan profiles for Linux and Windows platforms, designed to streamline your C/C++ project builds.

## Supported Platforms and Configurations

### Linux
- **Compiler**: GCC 11
- **Generators**:
  - Unix Makefile
  - Ninja
- **Tested on**: Ubuntu Linux, WSL2

### Windows
- **Compilers**:
  - MSVC 2015 (v140)
  - MSVC 2019 (v142)
  - MSVC 2022 (v143)
- **Generators**:
  - MSBuild
  - Ninja
- **Tested on**: Windows 10 PowerShell, WSL2

## Naming Convention

Profiles follow this naming pattern:

```
A_Pattern.os_arch_compiler_std.Generator.Runtime.Buildtype
```

Examples:
- `win_x64_msvc191_std17.VS2017.Dynamic.Debug`
- `linux_x64_gcc11_std20.Make.Static.Debug`

Where:
- `os`: Operating system (win, linux)
- `arch`: Architecture (x64, x86)
- `compiler`: Compiler version
- `std`: C++ standard version
- `Generator`: Build system generator
- `Runtime`: Runtime linkage (Dynamic/Static)
- `Buildtype`: Build configuration (Debug/Release)

## Requirements

- Conan 1.66 or Conan 2.1 (not yet tested with latest Conan versions)
- On Windows: Visual Studio 2015/2019/2022 installed
- On Linux: GCC 11 installed

## Known Issues

- **WSL1**: Due to filesystem bugs in WSL1, Conan may not work correctly. Please use WSL2 instead.

## Usage

1. Copy the desired profile files to your Conan profiles directory (typically `~/.conan/profiles` on Linux or `%USERPROFILE%\.conan\profiles` on Windows)
2. Or use with Conan commands:

```bash
conan install . --profile=path/to/conan-profiles/linux_x64_gcc11_std20.Make.Static.Debug
```

or

```powershell
conan install . --profile=path/to/conan-profiles/win_x64_msvc191_std17.VS2017.Dynamic.Debug
```

## Contribution

If you find any issues or want to add new profiles, please open an issue or submit a pull request.

## License

This repository is distributed under MIT license  term

