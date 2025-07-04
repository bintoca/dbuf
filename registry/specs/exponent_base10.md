## exponent_base10

ID: 27

Used for the exponent of decimal floating point numbers with arbitrary range and precision.

A decimal floating point number is structured as a map with [value](./value.md) representing the mantissa of the number.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Decimal floating point with value 1.01 | `0x029b950196457665` | (([type_map](./type_map.md) [exponent_base10](./exponent_base10.md) [value](./value.md) ([type_map](./type_map.md) [integer_signed](./integer_signed.md) [parse_varint](./parse_varint.md)) ([parse_bit_size](./parse_bit_size.md) 8)) (map (map 6) 101)) | <pre>1.01</pre> |