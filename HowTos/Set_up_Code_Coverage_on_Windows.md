# Set up C++ Code Coverage on Windows

<!-- toc -->
## Contents

  * [Visual Studio](#visual-studio)
    * [Line coverage in Visual Studio](#line-coverage-in-visual-studio)
    * [Branch coverage in Visual Studio](#branch-coverage-in-visual-studio)
  * [CLion](#clion)
    * [Line coverage in CLion](#line-coverage-in-clion)<!-- endToc -->

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

### Line coverage in CLion

As of [CLion 2020.2 EAP](https://blog.jetbrains.com/clion/2020/06/clion-2020-2-eap3-coverage-wsl-git-inspections/#code_coverage), CLion's Coverage feature now works for the *Clang-cl* compiler.

