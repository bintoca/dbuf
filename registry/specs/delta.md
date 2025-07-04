## delta

ID: 37

Used for compression of similar values in arrays by specifing the change from the previous item.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array with values (100, 102) | `0x121401a542603248` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [parse_varint](./parse_varint.md) ([type_map](./type_map.md) [delta](./delta.md) [parse_varint](./parse_varint.md)))) (array (choice 0 100) (choice 1 (map 2)))) | <pre>[100,102]</pre> |