## flatten_array

ID: 36

Signifies a nested array should be interpreted as flattened into the parent array.

Useful for compression of a large array when sections of the array have greater commonality.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of numbers with a size of 2 bits in one section and a size of 16 bits in another section | `0x101a421151158f213489c4138800` | (([type_array](./type_array.md) ([type_map](./type_map.md) [flatten_array](./flatten_array.md) ([type_choice](./type_choice.md) ([type_array](./type_array.md) ([parse_bit_size](./parse_bit_size.md) 2)) ([type_array](./type_array.md) ([parse_bit_size](./parse_bit_size.md) 16))))) (array (map (choice 0 (array 1 2))) (map (choice 1 (array 10000 20000))))) | <pre>[1,2,10000,20000]</pre> |