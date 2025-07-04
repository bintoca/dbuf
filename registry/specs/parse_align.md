## parse_align

ID: 13

Defines an instruction to align the parser to a multiple of bits.

Consumes one varint specifying the power of two number of bits, offset by one. (E.g. 0 = 2 bits, 1 = 4 bits, 2 = 8 bits, etc). Then consumes one symbol defining the nested type.

When encountered in the parsing of a data component: Consumes the least number of bits that bring the parser into the specified alignment. Then executes any data component parsing rules of the nested type.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Align to 32 bits before parsing varint | `0x8d44000050` | (([parse_align](./parse_align.md) 32 [parse_varint](./parse_varint.md)) (align 5)) | <pre>5</pre> |