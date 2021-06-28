# Set up C++ Code Coverage on Windows

<!-- toc -->
## Contents

  * [Visual Studio](#visual-studio)
    * [Line coverage in Visual Studio](#line-coverage-in-visual-studio)
    * [Branch coverage in Visual Studio](#branch-coverage-in-visual-studio)
  * [CLion](#clion)
    * [Set up clang-cl in CLion on Windows](#set-up-clang-cl-in-clion-on-windows)
    * [Enable exceptions for clang-cl](#enable-exceptions-for-clang-cl)
    * [CLion Native Coverage Tool - Line Coverage](#clion-native-coverage-tool---line-coverage)
    * [C/C++ Coverage Plugin - Line and Branch Coverage](#cc-coverage-plugin---line-and-branch-coverage)<!-- endToc -->

## Visual Studio

### Line coverage in Visual Studio

[OpenCppCoverage](https://github.com/OpenCppCoverage/OpenCppCoverage) has a Visual Studio plugin called [OpenCppCoveragePlugin](https://github.com/OpenCppCoverage/OpenCppCoveragePlugin) which can be used to collect line-coverage measurements in Visual Studio.

1. Install Visual Studio plugin called [OpenCppCoveragePlugin](https://github.com/OpenCppCoverage/OpenCppCoveragePlugin)
2. Restart Visual Studio
3. Build your program
4. Click "Run OpenCppCoverage" in Visual Studio's Tools menu

### Branch coverage in Visual Studio

I have had good results with the commercial tool [BullseyeCoverage](https://www.bullseye.com).

## CLion

I have found that code coverage in CLion on Windows only works well if you have installed and are using clang-cl, downloaded from LLVM.

### Set up clang-cl in CLion on Windows

1. Download the newest version of clang
    1. Go to https://releases.llvm.org/download.html
    2. Following the link to the GitHub release page
    3. Search the download page for `-win64` 
        1. you will find a match something like `LLVM-12.0.0-win32.exe`
    4. Download the .exe
        1. for example https://github.com/llvm/llvm-project/releases/download/llvmorg-12.0.0/LLVM-12.0.0-win64.exe
2. Install the downloaded LLVM executable
    1. This will install clang-cl in `C:\Program Files\LLVM\bin\clang-cl.exe`
3. Create a new CLion Toolchain to use the clang-cl you just installed
    1. This is documented under [Toolchains](https://www.jetbrains.com/help/clion/2021.1/toolchains.html)
    2. Go to `File | Settings | Build,Execution, Deployment | Toolchains`
    3. You can duplicate an existing Visual Studio Toolchain
    4. The specific settings I apply are:
        1. Name: **Visual Studio clang**
        2. Architecture: **x86_amd64**
        3. C Compiler: **C:\Program Files\LLVM\bin\clang-cl.exe**
        4. C++ Compiler: **C:\Program Files\LLVM\bin\clang-cl.exe**
4. Create a new CLion CMake Profile that uses your new Toolchain
    1. This is documented under [CMake](https://www.jetbrains.com/help/clion/2021.1/cmake0.html)
    2. Go to `File | Settings | Build,Execution, Deployment | CMake`
    3. You can duplicate an existing Profile
    4. The specific settings I apply are:
        1. Name: **Debug-Visual Studio clang**
        2. Build type: **Debug**
        3. Toolchain: **Visual Studio clang** (that is, the Toolchain you created in the previous step)

### Enable exceptions for clang-cl

If you are using Approval Tests, building with clang-cl will probably give you errors like this:

```
C:\Code\TestingLegacyCodeCourse.cpp\third_party/ApprovalTests.v.10.3.0.hpp(3022,13):
error: cannot use 'throw' with exceptions disabled
            throw ApprovalMissingException(receivedPath, approvedPath);
            ^
```

You can edit your top-level CMakeLists.txt file to add these lines, after the `project(...)` line:

```cmake
if (MSVC)
    # Enable exceptions for clang-cl
    add_compile_options(/EHsc)
endif ()
```

### CLion Native Coverage Tool - Line Coverage

The [CLion Code Coverage Documentation](https://www.jetbrains.com/help/clion/2021.1/code-coverage-clion.html) shows how to set up code coverage in general.

However the following steps may be all you need, after you have installed clang-cl in the earlier section.

You should now be able to select the **Debug-Visual Studio clang** CMake Profile in CLion and use `Run | Run [program-name] with Coverage`.

The first time you do this, the tests will run and CLion will likely show a pink box that says:

```
Could not find code coverage data
Make sure the target application is compiled with the required compiler options.
Would you like to add them automatically?
Fix and rerun
```

**Click the blue "Fix and rerun" text**, and CLion will create a new CMake profile, with the name " Coverage" added.

From this point on, with that Coverage profile, you will be able to `Run | Run [program-name] with Coverage`.

### C/C++ Coverage Plugin - Line and Branch Coverage

There is a CLion plugin called [C/C++ Coverage](https://plugins.jetbrains.com/plugin/11031-c-c--coverage) that provides more thorough code coverage data and presentation than the built-in CLion coverage facility.

Its [GitHub page](https://github.com/zero9178/C-Cpp-Coverage-for-CLion/blob/master/README.md) has some useful notes and background information.

However the following steps may be all you need, after you have installed clang-cl in the earlier section.

1. Install the C/C++ Coverage Plugin
    1. Go to `File | Settings | Plugins`
    2. Click Marketplace
    3. Search for Coverage
    4. Click on **C/C++ Coverage**
    5. Click Install
    6. Accept the prompt to re-start CLion

You should now be able to select the **Debug-Visual Studio clang** CMake Profile in CLion and use `Run | Run [program-name] with C/C++ Coverage Plugin`.


The first time you do this, the tests will run and CLion will likely show a grey box that says:

```
Missing compilation flags
Compiler flags for generating coverage are missing. Would
you like to creae a new profile with them now? Create
```

**Click the blue "Create" text**, and the plugin will create a new CMake profile, with the name " Coverage" added.

From this point on, with that Coverage profile, you will be able to `Run | Run [program-name] with C/C++ Coverage Plugin`.
