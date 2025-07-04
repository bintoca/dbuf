## registry_symbol_not_accepted

ID: 66

Symbol for validation errors caused by a specific registry symbol during parsing.

Specifications may limit accepted registry symbols to reduce parser complexity and resource usage.

A related stream position includes the bits of the offending symbol.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Error stating a symbol is not accepted at bit position 12 | `0x02a0c044c04248c0` | (([type_map](./type_map.md) [error](./error.md) [stream_position](./stream_position.md) [registry_symbol_not_accepted](./registry_symbol_not_accepted.md) [parse_varint](./parse_varint.md)) (map 12)) | <pre>{"error":"registry_symbol_not_accepted","stream_position":12}</pre> |