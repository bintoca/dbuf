## prefix

ID: 42

Used for compression of strings that begin with the same substring.

When used in a map with [value](./value.md) the unpacked value is a concatenation of the bytes of prefix and value

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| String "world" with prefix "hello " | `0x02aa95666068656c6c6f2050776f726c64` | (([type_map](./type_map.md) [prefix](./prefix.md) [value](./value.md) [parse_text](./parse_text.md) [parse_text](./parse_text.md)) (map (u8Text) (u8Text))) | <pre>"hello world"</pre> |