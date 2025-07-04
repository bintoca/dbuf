## parse_bytes

ID: 15

Symbol for parsing binary data as a sequence of bytes.

When encountered in the parsing of a data component: Consumes one varint specifying the length in bytes, then the number of bytes starting from the next 8-bit alignment.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| 3 bytes | `0x8f30010203` | ([parse_bytes](./parse_bytes.md) (bytes)) | <pre>{"0":1,"1":2,"2":3}</pre> |