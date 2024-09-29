## System
System object is a suite of methodologies used to build, secure, and maintain a single system.

Categories are well-defined code objects that are made up of partitions, which provide coverage to various requirements.

Partitions are displayed in order they are intended to be switched from being included, to delayed or reduced due to time constraints.

Analyzer has ability to test system with a specific configuration - it has configurations for test target, test settings, binary settings, and test type. Distinction between test and binary settings is made in order to enable testing to be conducted that uses different compiler flags than default ones in binary settings.

Maintainer describes tasks that are performed continuously in order to keep system up to date.

### Builder
#### Category
    - Module        (Must contain at least one state/reader/writer/function/
                     module - if it contains states, it must be possible to
                     explicitly set states for testing purposes)
    - Reader        (Function that must only output data from world - cannot
                     contain any testable logic)
    - Writer        (Function that only writes data to world - cannot contain any
                     testable logic)
    - Function      (Function that takes input, produce output/change module
                     states, and only factor in explicit arguments given by user,
                     and/or module states in order to calculate this. Writers
                     andreaders must be given as argument in order to produce
                     side effects on and/or read from the world, respectively)

#### Partition (Included, Delayed, Reduced)
    1. Binary size tests
    2. Private interface
    3. Performance tests
    4. Memory consumption tests
    5. Style/practices guide
    6. Tailored static analysis
    7. Implementation
    8. Documentation
    9. Public interface
    10. Abstract specification
    11. Functional tests with analysis

### Analyzer
    Target: (UserInterface, DeveloperInterface, Implementation)
    Test: (Windows, Linux, OSX, Android, iOS, x86_64, x32, ARM64, ARM32, Clang, GCC, MSVC)
    Binary: (Windows, Linux, OSX, Android, iOS, x86_64, x32, ARM64, ARM32, Clang, GCC, MSVC)
    Type: (FunctionalTestsWithAnalysis, NonFunctionalTests, TailoredStaticAnalysis, TestCoverage)


### Maintainer
    - Improve all tests
    - Fix security vulnerabilities
    - Update system with new intelligence
    - Add/remove features from system based on user feedback
    - Reduce system dependency on other systems/users
    - Reduce system/user dependency on this system
