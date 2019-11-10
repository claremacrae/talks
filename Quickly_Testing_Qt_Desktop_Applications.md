# Quickly Testing Qt Desktop Applications

* **Structuring projects to add tests**
    * [Arne Mertz's "Hello CMake" series](https://arne-mertz.de/2018/05/hello-cmake/)
* **C++ Test Frameworks and Qt**
    * Qt Test
        * [Qt's "Qt Test" home page](https://doc.qt.io/qt-5/qttest-index.html)
        * [Qt's "Qt Test C++ Classes" reference page](https://doc.qt.io/qt-5/qttest-module.html)
        * [Qt's "Writing Unit Tests"](https://wiki.qt.io/Writing_Unit_Tests) - now in transit to new location: [Qt Test Best Practices](https://doc-snapshots.qt.io/qt5-5.13/qttest-best-practices-qdoc.html)
        * [Qt's "Writing good tests"](https://wiki.qt.io/Writing_good_tests)
        * Example: [QGIS Unit Testing](https://docs.qgis.org/3.4/en/docs/developers_guide/unittesting.html) and [QGIS's test code](https://github.com/qgis/QGIS/tree/master/tests)
        * Generally useful pages
            * [Increase your QTest productivity](https://marcoarena.wordpress.com/tag/qtest-fixture/) - another auto-registering mechanism, how to create fixtures, and colour-coding test output
            * [ICS's slides on "QtTest Unit Testing Framework"](https://www.slideshare.net/ICSinc/qt-test-framework) - with a link to the video of the talk
    * Catch2
        * [FrogLogic's "Unit tests for Qt-based applications with Catch"](https://www.froglogic.com/blog/tip-of-the-week/unit-tests-for-qt-based-applications-with-catch/)
    * Google Test and Google Mock
        * [ICS's slides on "Qt Test-Driven Development Using Google Test and Google Mock"](https://www.slideshare.net/ICSinc/webinar-qt-testdriven-development-using-google-test-and-google-mock)
* **Approval Tests**
    * [ApprovalTests.cpp](https://github.com/approvals/ApprovalTests.cpp)
    * [ApprovalTests.cpp.StarterProject](https://github.com/approvals/ApprovalTests.cpp.StarterProject)
    * [ApprovalTests.cpp.Qt](https://github.com/approvals/ApprovalTests.cpp.Qt)
    * [ApprovalTests.cpp.Qt.StarterProject](https://github.com/approvals/ApprovalTests.cpp.Qt.StarterProject)
* **Continuous Integration**
    * [Travis CI's "GUI and Headless Browser Testing"](https://docs.travis-ci.com/user/gui-and-headless-browsers/)
* Tools
    * [KDAB GammaRay](https://www.kdab.com/development-resources/qt-tools/gammaray/)
* **Refactoring - once code is tested**
    * [Llewellyn Falco and Woody Zuill's "Practical Refactoring: 2 Minutes to Better Code"](https://youtu.be/aWiwDdx_rdo)

### Clare Macrae

* Blog
* Presentations
* Hire Me

### Appendix

* **Qt Test executables**
    * Qt Tests only supports one test QObject per executable, generating large numbers of exes
    * Various people have tried to work around this - the following links may be useful
        * [Unofficial Qt Creator Blog on "Running Multiple Unit Tests" in one Qt Test program](http://qtcreator.blogspot.com/2009/10/running-multiple-unit-tests.html)
        * [Jaded Biologist on "Using QtTest Effectively"](https://alexhuszagh.github.io/2016/using-qttest-effectively/)
