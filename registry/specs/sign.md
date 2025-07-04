## sign

ID: 69

Used for the positive or negative sign of a number.

A sign/magnitude number is structured as a map with additional keys representing the magnitude.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Number with value -2 | `0x02c04595504900` | (([type_map](./type_map.md) [sign](./sign.md) [value](./value.md) ([parse_bit_size](./parse_bit_size.md) 1) [parse_varint](./parse_varint.md)) (map 1 2)) | <pre>-2</pre> |
| Number with value -2 with boolean choice | `0x02c045952193944900` | (([type_map](./type_map.md) [sign](./sign.md) [value](./value.md) ([type_choice](./type_choice.md) [false](./false.md) [true](./true.md)) [parse_varint](./parse_varint.md)) (map (choice 1) 2)) | <pre>-2</pre> |