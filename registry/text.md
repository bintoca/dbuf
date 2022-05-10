# DBUF Text Symbols

Subject to change until core semantics are settled

A string or a substring is considered a Scope in the [codec](../codec.md)

### Start of substring
- ID: 0

### End of string or substring
- ID: 1

### Back reference
- ID: 2
- Used to repeat previously seen data
- Consumes next varint as distance
- Zero based, a distance of zero means the first eligible Item closest to the current position
- Eligible Items include:
  - Substrings in the current string
  - Non-text Scopes in the current string
  - Scopes before the start of the current string according to non-text [`back_reference`](./specs/back_reference.md) rules
- Supports chaining, a back reference to a back reference propagates the original Item
- A string defined as rich text can have back references to non-text data
- A string defined as plain text must not have back references to non-text data
- A distance that extends past the beginning of the root Scope throws [`error_invalid_back_reference`](./specs/error_invalid_back_reference.md) 

### Space
- ID: 3
- Unicode mapping: U+0020

### Letter a
- ID: 4
- Unicode mapping: U+0061

### Letter e
- ID: 5
- Unicode mapping: U+0065

### Letter o
- ID: 6
- Unicode mapping: U+006F

### Letter t
- ID: 7
- Unicode mapping: U+0074

### Repeat
- ID: 8
- Used for run length encoding
- Consumes next varint as number of repetitions + 1 of previous value

### Non-text
- ID: 9
- Used for embedding structured data in a rich text string
- Invalid in a plain text string
- Begins a Scope that uses the default registry symbols, an end scope symbol returns parsing to the text scope
- Text and non-text can be nested recursively

### Line feed
- ID: 10
- Unicode mapping: U+000A

### Exclamation
- ID: 11
- Unicode mapping: U+0021

### Comma
- ID: 12
- Unicode mapping: U+002C

### Hyphen
- ID: 13
- Unicode mapping: U+002D

### Period
- ID: 14
- Unicode mapping: U+002E

### Question
- ID: 15
- Unicode mapping: U+003F

### Remaining A-Z, a-z not defined above
- ID: 16-63
- Unicode mapping: U+0041-U+005A, U+0061-U+007A

### Remaining ASCII not defined above
- ID: 64-132
- Unicode mapping: U+0000-U+007F

### Remaining unicode not defined above
- ID: 133-1114116
- Unicode mapping: U+0080-U+10FFFF