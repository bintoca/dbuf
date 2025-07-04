## error

ID: 32

Used as a key in a map to identify error information.

[error](./error.md) must be the first key in a map with more than one key.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Internal error | `0x01a0c040` | (([type_map](./type_map.md) [error](./error.md) [error_internal](./error_internal.md)) (map)) | <pre>{"error":"error_internal"}</pre> |