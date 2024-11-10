## Grammar
Grammer object contains rules of a grammar - is intended to prevent and detect errors in translation from intention to writing.

### Objects

#### Letter
    8
Integer that represents a unique symbol.

#### Placeholder
    'A
    ^['A]
Represents either a letter or syllable. A syllable may be placed inside of
itself infinitely many times, like so:

    ['A: (8 O 9)]('B, 8 O ^['A] O 10)

In this example, 'A' is expanded in middle of own body.

#### Syllable
    ('A, 8 O 9 O 10)
    ['A: (8 O 9)]('B, 8 O 9 O 'A O, 'A)

A group of letters or other syllables, may be recursive.

#### Grammar
    (^G, 30)
A map of syllables that defines a number of unique letters, and can coinain a set of syllables and references to letters that are available in a grammer - enforces uniqueness of letters and non-overlap of all syllables, and use of all letters in grammer. Syllables cannot be nested without inner syllables being expanded from a label.

### Operations
#### Mint
    ('C, 'A O 'B O 31)->G

Adds a new syllable to grammer, changing letters to unused ones still available in grammer, which consumes them - reusing some existing syllables and/or letters, if requested. Fails if there are not enough letters available in grammer, syllable would overlap with one or more existing syllables, or label is already taken by another syllable/letter. All syllables in grammer must differ by at least two letters in order to protect against mistyping and misunderstanding.

### Relations
#### Union
    2 V 3
    'A V 'B
    2 V ('U)3

A selection between two or more syllables or letters - can be tagged and/or only activated if a tag in another union is active.

