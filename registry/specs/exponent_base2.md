## exponent_base2

ID: 26

Used for the exponent of binary floating point numbers with arbitrary range and precision.

A binary floating point number is structured as a map with [value](./value.md) representing the mantissa of the number.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Binary floating point with value 2.125 | `0x029a950196454110` | (([type_map](./type_map.md) [exponent_base2](./exponent_base2.md) [value](./value.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) [parse_varint](./parse_varint.md)) ([parse_bit_size](./parse_bit_size.md) 5)) (map (map 1) 2)) | <pre>2.125</pre> |