# Set up C++ Code Coverage on macOS

## Line coverage with CMake in CLion

I got this setup working on macOS:

* install:
    * g++-8
    * lcov
* Use [`CodeCoverage.cmake`](https://github.com/bilke/cmake-modules/blob/master/CodeCoverage.cmake) from [github.com/bilke/cmake-modules](https://github.com/bilke/cmake-modules) to adjust compiler arguments

Here is how to use `CodeCoverage.cmake` to set up to use CLion's "Run with Coverage" button: add these lines in your top-level CMakeLists.txt file, before you add set any targets or add any sub-directories: 

```cmake
# Provide path for scripts
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/CMake")

project(...)

# If building the code with clang gives 'Error: could not load cache'
#   1 turn COLLECT_CODE_COVERAGE to FALSE
#   2 build and run the tests
#   3 turn COLLECT_CODE_COVERAGE back to TRUE
set(COLLECT_CODE_COVERAGE TRUE)
if (COLLECT_CODE_COVERAGE)
    include(CodeCoverage)
    append_coverage_compiler_flags()
    set(COVERAGE_EXCLUDES
            "/Applications/Xcode.app/*"
            "/opt/local/*"
            "third_party/*"
            )
endif () 
```

## Branch coverage with CMake

As of June 2020, CLion only supports line-coverage and not branch coverage. So any measuring of branch coverage needs to be done by some other mechanism.

`CodeCoverage.cmake` provides a way to do this.

* Add these lines to you `~/.lcovrc`
    ```
    genhtml_branch_coverage = 1
    lcov_branch_coverage = 1
    lcov_excl_br_line = LCOV_EXCL_BR_LINE|CHECK|REQUIRE
    ```
* Edit the CMake for your exe to add something like this:

```cmake
set(EXE_NAME GildedRose)

# Set up your executable in the normal way
add_executable(${EXE_NAME}
        main.cpp
        ...
        )

# If code coverage is enabled, add a new target, called GildedRose_branch_coverage.
# Building this target will run the tests, collect coverage stats, and generate
# an HTML report with branch coverage (if you have correctly adjusted your
# ~/.lcovrc file)
if (COLLECT_CODE_COVERAGE)
    set(COVERAGE_TARGET ${EXE_NAME}_branch_coverage)
    setup_target_for_coverage_lcov(
            NAME ${COVERAGE_TARGET}
            EXECUTABLE ${EXE_NAME}
            DEPENDENCIES ${EXE_NAME})
endif ()
```

For more details, see the comments in [`CodeCoverage.cmake`](https://github.com/bilke/cmake-modules/blob/master/CodeCoverage.cmake).

Once this is set up, you can choose the "..._branch_coverage" target in CLion and then build it. This will generate a set of HTML reports, and print out a partial path to the output files, which you then have to navigate to, to open the output.

