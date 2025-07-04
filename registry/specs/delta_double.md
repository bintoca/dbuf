## delta_double

ID: 38

Used for compression of similar values in arrays by specifing the change of the delta from the previous item.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array with values (100, 210, 320) | `0x121401a643603262a0` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [parse_varint](./parse_varint.md) ([type_map](./type_map.md) [delta_double](./delta_double.md) [parse_varint](./parse_varint.md)))) (array (choice 0 100) (choice 1 (map 10)) (choice 1 (map 0)))) | <pre>[100,210,320]</pre> |