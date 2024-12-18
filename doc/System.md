## System
System object is a suite of methodologies used to build, secure, and maintain a single system.

Categories are well-defined code objects that are made up of partitions, which provide coverage to various requirements.

Partitions are displayed in order they are intended to be switched from being included, delayed to be implemented at a later time, or reduced respectively in order to meet time constraints.

Analyzer has ability to test system with a specific configuration - it has configurations for test target, test settings, binary settings, and test type. Distinction between test and binary settings is made in order to enable testing to be conducted that uses different compiler flags than default ones in binary settings.

### Builder
#### Category
    - Module            (Set that contains at least one module/structure/reader/writer/function/
                         abstract class/concrete class - if it contains structures, it must be
                         possible to explicitly set structure states for testing purposes)
    - Structure         (A class with only public getter and setter methods, constructors, and an
                         implementation-defined data layout - it must be possible to explicitly set
                         structure states for testing purposes. A class may non-virtually inherit from
                         one or more other classes)
    - Reader            (Function that both takes no arguments, and outputs a single structure
                         containing info from world - cannot contain any testable logic)
    - Writer            (Function that takes a single structure as an argument,
                         writes data to world, and outputs nothing - cannot contain any testable logic)
    - Function          (Function that takes zero or more structures and/or functions as
                         arguments, produces outputs, and only factors in explicit arguments given by
                         user in order to calculate this. Writers and/or readers must be given as
                         arguments in order to produce side effects on and/or get info from the world, respectively)

#### Partition (Included, Delayed, Reduced)
    1. Binary size tests
    2. Private interface
    3. Performance tests
    4. Memory consumption tests
    5. Style/practices guide
    6. Static analysis
    7. Implementation
    8. Documentation
    9. Public interface
    10. Functional tests with analysis

### Analyzer
    Target: (UserInterface, DeveloperInterface, Implementation)
    Test: (Windows, Linux, OSX, Android, iOS, x86_64, x32, ARM64, ARM32, Clang, GCC, MSVC)
    Binary: (Windows, Linux, OSX, Android, iOS, x86_64, x32, ARM64, ARM32, Clang, GCC, MSVC)
    Type: (FunctionalTestsWithAnalysis, NonFunctionalTests, StaticAnalysis, TestCoverage)