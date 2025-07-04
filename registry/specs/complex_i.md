## complex_i

ID: 71

Used for the imaginary part of complex numbers.

A complex number is structured as a map with [value](./value.md) representing the real part of the number.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Complex number with value 2 + 3i | `0x02c047954432` | (([type_map](./type_map.md) [complex_i](./complex_i.md) [value](./value.md) [parse_varint](./parse_varint.md) [parse_varint](./parse_varint.md)) (map 3 2)) | <pre>{"complex_i":3,"value":2}</pre> |