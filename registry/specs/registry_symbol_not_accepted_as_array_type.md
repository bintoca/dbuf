## registry_symbol_not_accepted_as_array_type

ID: 67

Symbol for validation errors caused by a specific registry symbol during parsing of array types.

Specifications may limit accepted registry symbols to reduce parser complexity and resource usage.

A related stream position includes the bits of the offending symbol.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Error stating a symbol is not accepted at bit position 12 | `0x02a0c044c04348c0` | (([type_map](./type_map.md) [error](./error.md) [stream_position](./stream_position.md) [registry_symbol_not_accepted_as_array_type](./registry_symbol_not_accepted_as_array_type.md) [parse_varint](./parse_varint.md)) (map 12)) | <pre>{"error":"registry_symbol_not_accepted_as_array_type","stream_position":12}</pre> |