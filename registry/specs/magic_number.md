## magic_number

- Begins a one Item Scope
- Semantically ignored wrapper around the inner Item
- Optional first symbol of a stream that creates a distinct bit pattern to distinguish from other file formats
- Fills one varint block
- Use 0 value for description bits creating first byte of 0x00
- 2nd, 3rd, 4th, bytes will spell 'DBU' in ASCII