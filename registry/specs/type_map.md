## type_map

ID: 0

Defines a collection of key/value pairs.

Consumes one varint specifying the number of pairs to parse. All the keys come first followed by all the values.

When encountered in the parsing of a data component: Each key or value that has data component parsing rules is executed.

Type component values and data component values combine to form a logical map. If an array of maps all have the same value for a key, that value can be specified once in the type component and omittted in the data component.

If the same key is specified more than once, the unpacking procedure combines the values into an array. If the first value is an array, the following values are appended to the first array. If following values are arrays, they are appended as nested, not flattened into the first array.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Two keys with unsigned integer values | `0x02c046954434` | (([type_map](./type_map.md) [denominator](./denominator.md) [value](./value.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)) (map 3 4)) | <pre>{"denominator":3,"value":4}</pre> |
| Array of maps with value in the type component | `0x102c046957424247` | (([type_array](./type_array.md) ([type_map](./type_map.md) [denominator](./denominator.md) [value](./value.md) ([parse_varint](./parse_varint.md) 2) [parse_varint](./parse_varint.md))) (array (map 4) (map 7))) | <pre>[{"denominator":2,"value":4},{"denominator":2,"value":7}]</pre> |
| Key specified twice | `0x03c04695c046444345` | (([type_map](./type_map.md) [denominator](./denominator.md) [value](./value.md) [denominator](./denominator.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)) (map 3 4 5)) | <pre>{"denominator":[3,5],"value":4}</pre> |
| Key specified twice with array as first value | `0x03c04695c04614441345` | (([type_map](./type_map.md) [denominator](./denominator.md) [value](./value.md) [denominator](./denominator.md) ([type_array](./type_array.md) [parse_varint](./parse_varint.md)) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)) (map (array 3) 4 5)) | <pre>{"denominator":[3,5],"value":4}</pre> |