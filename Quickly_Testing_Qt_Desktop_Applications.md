<a id="top"></a>

# Quickly Testing Qt Desktop Applications

## Demo Code

* This talk is partly demo-based
* The demo code is at:
    * [github.com/claremacrae/approvals_live_demo](https://github.com/claremacrae/approvals_live_demo/)
    * As I give this talk, I tag the versions presented, as the demos and ApprovalTests.cpp library will evolve over time:
        * [Tag: 2020-09-cppcon](https://github.com/claremacrae/approvals_live_demo/tree/2020-09-cppcon/): CppCon 2020, 16 September 2020

## Links

* [Approval Tests](https://approvaltests.com)
    * [ApprovalTests.cpp](https://github.com/approvals/ApprovalTests.cpp)
    * [ApprovalTests.cpp.StarterProject](https://github.com/approvals/ApprovalTests.cpp.StarterProject)
    * [ApprovalTests.cpp.Qt](https://github.com/approvals/ApprovalTests.cpp.Qt)
    * [ApprovalTests.cpp.Qt.StarterProject](https://github.com/approvals/ApprovalTests.cpp.Qt.StarterProject)
* [Arne Mertz's "Hello CMake" series](https://arne-mertz.de/2018/05/hello-cmake/)
* [Catch2 test framework](https://github.com/catchorg/Catch2)
    * [FrogLogic's "Unit tests for Qt-based applications with Catch"](https://www.froglogic.com/blog/tip-of-the-week/unit-tests-for-qt-based-applications-with-catch/)
    * [Catch2 test command-line arguments](https://github.com/catchorg/Catch2/blob/master/docs/command-line.md)
* [clazy - Qt related compiler warnings and fixits](https://github.com/KDE/clazy)
    * [old-style-connect](https://github.com/KDE/clazy/blob/master/docs/checks/README-old-style-connect.md) - but do read the caveats.
* [Clare Macrae's "Quickly Testing Legacy Code" talk at C++ on Sea 2019](https://www.youtube.com/watch?v=dtm8V3TIB6k)
* [Googletest - Google Testing and Mocking Framework](https://github.com/google/googletest)
    * [ICS's slides on "Qt Test-Driven Development Using Google Test and Google Mock"](https://www.slideshare.net/ICSinc/webinar-qt-testdriven-development-using-google-test-and-google-mock)
* [KDAB GammaRay](https://www.kdab.com/development-resources/qt-tools/gammaray/)
* [Llewellyn Falco and Woody Zuill's "Practical Refactoring: 2 Minutes to Better Code"](https://youtu.be/aWiwDdx_rdo)
* [Qt](https://www.qt.io)
    * [Qt Test framework](https://doc.qt.io/qt-5/qttest-index.html)
    * [Qt's "Writing Unit Tests"](https://wiki.qt.io/Writing_Unit_Tests) - now in transit to new location: [Qt Test Best Practices](https://doc-snapshots.qt.io/qt5-5.13/qttest-best-practices-qdoc.html)
    * [Qt's "Writing good tests"](https://wiki.qt.io/Writing_good_tests)
    * [ICS's slides on "QtTest Unit Testing Framework"](https://www.slideshare.net/ICSinc/qt-test-framework) - with a link to the video of the talk
    * [QApplication command-line arguments](https://doc.qt.io/qt-5/qguiapplication.html#QGuiApplication)
        * [Supported platform names](https://doc.qt.io/qt-5/qguiapplication.html#platformName-prop) - for example, run your tests with `-platform offscreen` to avoid Widgets flashing up
* [Squish GUI Test Automation Tool](https://www.froglogic.com/squish/)
    * Coming soon: [Frerich Raabe's "Behavior-Driven GUI Test Automation of Qt Applications"](https://www.qtdesktopdays.com/timetable/event/behavior-driven-gui-test-automation-of-qt-applications/)
* [SuperCollider audio platform](https://supercollider.github.io)
* [Test Pyramid](https://martinfowler.com/bliki/TestPyramid.html)
* [Travis CI's "GUI and Headless Browser Testing"](https://docs.travis-ci.com/user/gui-and-headless-browsers/)
* [Xvfb](https://www.x.org/releases/X11R7.6/doc/man/man1/Xvfb.1.xhtml) - virtual framebuffer X server for X11
    * [Xvfb on Wikipedia](https://en.wikipedia.org/wiki/Xvfb)

### Clare Macrae

I am a consultant and trainer.

* [Website](https://claremacrae.co.uk)
* [Blog](https://claremacrae.co.uk/blog/)
* [Presentations](https://claremacrae.co.uk/conferences/presentations.html)
* [Hire Me](https://claremacrae.co.uk/consulting/hire_me.html)

### Appendix

* **Qt Test Info**
    * Example: [QGIS Unit Testing](https://docs.qgis.org/3.4/en/docs/developers_guide/unittesting.html) and [QGIS's test code](https://github.com/qgis/QGIS/tree/master/tests)
    * Generally useful pages
        * [Increase your QTest productivity](https://marcoarena.wordpress.com/tag/qtest-fixture/) - another auto-registering mechanism, how to create fixtures, and colour-coding test output
* **Qt Test executables**
    * Qt Tests only supports one test QObject per executable, generating large numbers of exes
    * Various people have tried to work around this - the following links may be useful
        * [Unofficial Qt Creator Blog on "Running Multiple Unit Tests" in one Qt Test program](http://qtcreator.blogspot.com/2009/10/running-multiple-unit-tests.html)
        * [Jaded Biologist on "Using QtTest Effectively"](https://alexhuszagh.github.io/2016/using-qttest-effectively/)
