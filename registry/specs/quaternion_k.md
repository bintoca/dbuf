## quaternion_k

ID: 73

Used for the k part of quaternion numbers.

A quaternion number is structured as a map with [quaternion_k](./quaternion_k.md), [quaternion_j](./quaternion_j.md), [complex_i](./complex_i.md) and [value](./value.md) for the real part of the number.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Quaternion number with value 2 + 3i + 4j + 5k | `0x04c049c048c0479544445432` | (([type_map](./type_map.md) [quaternion_k](./quaternion_k.md) [quaternion_j](./quaternion_j.md) [complex_i](./complex_i.md) [value](./value.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)) (map 5 4 3 2)) | <pre>{"quaternion_k":5,"quaternion_j":4,"complex_i":3,"value":2}</pre> |