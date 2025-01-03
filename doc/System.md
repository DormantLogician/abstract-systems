## System

System object is a suite of methodologies used to build, secure, and maintain a single system.

Categories are well-defined code objects that are made up of partitions, which provide coverage to various requirements.

Partitions are displayed in order they are intended to be switched from being included, delayed to be implemented at a later time, or reduced respectively in order to meet time constraints.

Analyzer has ability to test system with a specific configuration - it has configurations for test target, test settings, binary settings, and test type. Distinction between test and binary settings is made in order to enable testing to be conducted that uses different compiler flags than default ones in binary settings.

### Builder

#### Category

    - Module            (Set that gives access to at least one structure, reader, writer, function,
                         or module definition/declaration. Modules may be either public, where user
                         is outside of project, or private, where user is local to project)
    - Unit              (Either A strongly/weakly typed integer, or a decimal type, smart pointer
                         class, or non-structure class from outside of project)
    - Structure         (Either a unit, or a class with only public getter and setter methods,
                         constructors, and if inside a public module, and implementation-defined
                         data layout - it must be possible to explicitly set unit and/or structure
                         states for testing purposes if not a unit. Non-unit structures may only
                         non-virtually inherit from one or more other structures)
    - Reader            (Function that both takes no arguments, and outputs a single structure
                         containing info from world - cannot contain any testable logic)
    - Writer            (Function that takes a single unit or structure as an argument, writes data to
                         world, and outputs nothing - cannot contain any testable logic)
    - Function          (Takes zero or more units, structures, and/or functions as arguments, produces
                         outputs, and only factors in explicit arguments given by user in order to calculate
                         this. Writers and/or readers must be given as arguments in order to produce side
                         effects on and/or get info from the world, respectively)

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