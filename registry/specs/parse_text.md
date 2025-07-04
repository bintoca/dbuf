## parse_text

ID: 6

Symbol for parsing text as a string of UTF8 bytes.

When encountered in the parsing of a data component: Consumes one varint specifying the length in bytes, then the number of bytes starting from the next 8-bit alignment.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| String of text | `0x68b068656c6c6f20776f726c64` | ([parse_text](./parse_text.md) (u8Text)) | <pre>"hello world"</pre> |