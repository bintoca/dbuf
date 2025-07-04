## format

ID: 41

Describes a data format.

When used in a map with [value](./value.md) describes the format of that value.

If the format value is a fixed bit width unsigned integer or an array of fixed bit width unsigned integers, the bits are interpreted as the type component of a distinct DBUF stream. Any associated [value](./value.md) is interpeted as the data component of a DBUF stream.

If the format value is the [format](./format.md) symbol, the format is a complete DBUF stream.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Format for a DBUF type_array of varints | `0x01a98f1014` | (([type_map](./type_map.md) [format](./format.md) [parse_bytes](./parse_bytes.md)) (map (bytes))) | <pre>{"format":{"0":20}}</pre> |
| Format for a DBUF type_array of varints with array of varints (1,2,3) packed as bytes | `0x02a9958f8f1014203123` | (([type_map](./type_map.md) [format](./format.md) [value](./value.md) [parse_bytes](./parse_bytes.md) [parse_bytes](./parse_bytes.md)) (map (bytes) (bytes))) | <pre>{"format":{"0":20},"value":{"0":49,"1":35}}</pre> |
| Format for a DBUF stream | `0x01a9a9` | (([type_map](./type_map.md) [format](./format.md) [format](./format.md)) (map)) | <pre>{"format":"format"}</pre> |
| Format for a DBUF stream with type and array of varints (1,2,3) packed as bytes | `0x02a995a98f30143123` | (([type_map](./type_map.md) [format](./format.md) [value](./value.md) [format](./format.md) [parse_bytes](./parse_bytes.md)) (map (bytes))) | <pre>{"format":"format","value":{"0":20,"1":49,"2":35}}</pre> |