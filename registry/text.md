# DBUF Text Symbols

Subject to change until core semantics are settled

A string is considered a Scope in the [codec](../codec.md)

### End of string or substring
- ID: 0

### Space
- ID: 1
- Unicode mapping: U+0020

### Letter a
- ID: 2
- Unicode mapping: U+0061

### Letter e
- ID: 3
- Unicode mapping: U+0065

### Letter i
- ID: 4
- Unicode mapping: U+0069

### Letter n
- ID: 5
- Unicode mapping: U+006E

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

### Double Quote
- ID: 12
- Unicode mapping: U+0022

### Single Quote
- ID: 13
- Unicode mapping: U+0027

### Comma
- ID: 14
- Unicode mapping: U+002C

### Hyphen
- ID: 15
- Unicode mapping: U+002D

### Period
- ID: 16
- Unicode mapping: U+002E

### Question
- ID: 17
- Unicode mapping: U+003F

### Remaining A-Z, a-z not defined above
- ID: 18-63
- Unicode mapping: U+0041-U+005A, U+0061-U+007A

### Remaining ASCII not defined above
- ID: 64-130
- Unicode mapping: U+0000-U+007F

### Remaining unicode not defined above
- ID: 131-1114116
- Unicode mapping: U+0080-U+10FFFF