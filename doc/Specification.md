## Specification
Specification objects are behavioral descriptions of systems that are used to create concrete test suites.

Testing of systems is based on the presentation of a set of situations (sets of inputs) that describe when a specific outcome is expected to a system, then verifying expected outcome is produced for each of them. Combinatorics is used to provide coverage of situations for each possible outcome.

Methodology provides a way to create effective test suites for arbitrary systems in an adjustable amount of detail.

### Objects
#### Model
A set of features that represents capabilities of a system. Can be translated into a concrete test suite for system.

#### Feature
A function that takes one or more categories as arguments, and produces a single outcome. Each feature represents a single possible system behavior, and all situations where that behavior is expected.

#### Category
A type of input that may have one or more possible combinations of qualifiers. Categories may be used to divide inputs into partitions that system is designed to respond to.

#### Qualifier
A single bit that represents a trait a category may have - these are used to describe state of a specific category. Qualifiers may be either on, or off for a particular category.

#### Reference
Used to indicate that two or more inputs may refer to the same category instance -
for testing cases where same category instance is given as two or more arguments to a feature.

#### Array
An array of a particular category can be created to represent zero or more of that category.

### Model layout
First member of model defines a category that represents possible outcomes a system can produce, called the outcome - this is used to combinatorially generate features for all possible system behaviors.

Second member of model defines a set of categories to be used by features.

Third member of model defines a set of features and their respective situations, where each feature represents an intended behavior of system, and each situation represents when that behavior is expected.

### Built-in categories
Represents traits of outside world around system:

    Environment:
    - Minimum load
    - Typical load
    - Maximum load
    - Inconsistent load
    - No internet
    - Out of resource

Represents an abstract integer:

    Quantity:
    - -2
    - -1
    - 0
    - 1
    - 2
    - 3

Represents stored state information within system:

    State:
    - Default
    - Other

Represents an abstract input to system:

    Type:
    - Typical
    - Unusual
    - Left edge
    - Right edge
    - Part of own state

Default qualifiers for outcome category:

    Outcome:
    - Produces error
    - Produces result
    - Doesn't modify inputs
    - Performance requirements holding
    - Memory consumption requirements holding
    - Security requirements holding
