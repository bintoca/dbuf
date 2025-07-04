## prefix_delta

ID: 44

Used for compression of an array of strings that begin with similar substrings.

When used in a map with [value](./value.md) the unpacked value is a concatenation of the bytes of the previous value in the array minus the number of bytes specified by the delta and value

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of strings with partial shared prefixes | `0x102ac954630461626364146566676853696a6b` | (([type_array](./type_array.md) ([type_map](./type_map.md) [prefix_delta](./prefix_delta.md) [value](./value.md) [parse_varint](./parse_varint.md) [parse_text](./parse_text.md))) (array (map 0 (u8Text)) (map 1 (u8Text)) (map 5 (u8Text)))) | <pre>["abcd","abcefgh","abijk"]</pre> |