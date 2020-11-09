# Workshop: Testing Legacy Code Effectively with Approval Tests

<!-- toc -->
## Contents

  * [Next Training Session](#next-training-session)
  * [Course Materials](#course-materials)
  * [Approval Tests](#approval-tests)
  * [Techniques](#techniques)
  * [Links](#links)
  * [Trainers](#trainers)
    * [Clare Macrae](#clare-macrae)
    * [Llewellyn Falco](#llewellyn-falco)<!-- endToc -->

## Next Training Session

* [November 2020](https://bit.ly/LegacyCppNov2020)

## Course Materials

* [Resources](https://github.com/claremacrae/talks/blob/main/Workshop_Testing_Legacy_Code_Effectively_with_Approval_Tests.md#top) (this file)
* [Slides](https://github.com/LearnWithLlew/TestingLegacyCodeCourse.slides)
* [Code](https://github.com/LearnWithLlew/TestingLegacyCodeCourse.cpp)

## Approval Tests

* [Approval Tests](https://approvaltests.com)
    * [ApprovalTests.cpp](https://github.com/approvals/ApprovalTests.cpp)
    * [ApprovalTests.cpp.StarterProject](https://github.com/approvals/ApprovalTests.cpp.StarterProject)
* ApprovalTests.cpp User Guide
    * [User Guide on Read the Docs](https://approvaltestscpp.readthedocs.io/en/latest/)
    * [User Guide on GitHub](https://github.com/approvals/ApprovalTests.cpp/blob/master/doc/README.md#top)

## Techniques

* Peel and Slice
    * [Using ApprovalTests in .Net: Playlist](https://www.youtube.com/user/isidoreus)
    * [Using ApprovalTests in .Net 12 The Peel](https://www.youtube.com/watch?v=p0tILwRZH5Q)
    * [Using ApprovalTests in .Net 13 Mocks](https://www.youtube.com/watch?v=PY5msaYNPrI)
    * [Using ApprovalTests in .Net 14 Peel & Slice](https://www.youtube.com/watch?v=sXqRWXWiXYo)
* Getting code you can't build under test
    * See James Grenning's [Crash to Pass Toolkit](https://github.com/jwgrenning/gen-xfakes) 
    * James' article [TDD How-to: Get your Legacy C Into a Test Harness](https://wingman-sw.com/articles/tdd-legacy-c) also describes many patterns for getting legacy C code in to a test harness
* Commonly-asked questions about approval tests
    * [Testing exception messages](https://approvaltestscpp.readthedocs.io/en/latest/generated_docs/TestingExceptions.html)
    * [Controlling where Approval Tests puts the approved and received files](https://approvaltestscpp.readthedocs.io/en/latest/generated_docs/Configuration.html#using-sub-directories-for-approved-files)
* Emily Bache's [Approval Tools](https://github.com/emilybache/ApprovalTools) - some scripts for bulk-reviewing and approving Approval Tests failures

## Links

* How Approval Tests finds diff tools
  * [Supported diff tools](https://github.com/approvals/ApprovalTests.cpp/blob/master/doc/Reporters.md#supported-diff-tools)
  * [Locations that it searches for diff tools](https://github.com/approvals/ApprovalTests.cpp/blob/master/ApprovalTests/reporters/DiffPrograms.cpp): Note that they need to be installed in standard locations
* [Clare's C++ on Sea graphics-differencing talk](https://www.youtube.com/watch?v=dtm8V3TIB6k)
* [Regular Expressions 101](https://regex101.com/)

## Trainers

### Clare Macrae

* [Website](https://claremacrae.co.uk)
* [Blog](https://claremacrae.co.uk/blog/)
* [Presentations](https://claremacrae.co.uk/conferences/presentations.html)
* [Hire Me](https://claremacrae.co.uk/consulting/hire_me.html)

### Llewellyn Falco

* [Blog](http://llewellynfalco.blogspot.com/)
* [ApprovalTests](https://github.com/approvals/)
* [YouTube](https://www.youtube.com/user/isidoreus/videos)

