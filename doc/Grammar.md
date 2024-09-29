## Grammar
Grammer object contains rules of a grammar - is intended to prevent and detect errors in translation from intention to writing.

### Objects

#### Letter
    8
Integer that represents a unique symbol.


#### Placeholder
    'T
Represents either a letter or syllable.


#### Syllable
    (A: 8,9,10)   ['T:8,9](A: 8,9,'T,^['T,10,11])

A group of letters or other syllables, may be recursive.


#### Grammar
    (^G: 30)
A map of syllables that defines a number of unique letters, and can coinain a set of syllables and references to letters that are available in a grammer - enforces uniqueness of letters and non-overlap of all syllables, and use of all letters in grammer. Syllables cannot be nested without inner syllables being expanded from a label.

### Operations

#### Mint
    (C: 'A,'B,31)->G

Adds a new syllable to grammer, changing letters to unused ones still available in grammer, which consumes them - reusing some existing syllables and/or letters, if requested. Fails if there are not enough letters available in grammer, syllable would overlap with one or more existing syllables, or label is already taken by another syllable/letter. All syllables in grammer must differ by at least two letters in order to protect against mistyping and misunderstanding.

### Relations
#### Union
    'A|'B   2|3   2|('U)3

A selection between two or more syllables or letters - can be tagged and/or only activated if a tag in another union is active.

#### Continuation
    'A(2)('R)   'A(2->7)('R)   'A(')(*R)  'A(2->')('R)

Takes a recursive syllable as first input, and second a recursive syllable that represents a pattern - outputs a sequence of valid expansions of first syllable that fit into pattern.

