## suffix

ID: 43

Used for compression of strings that end with the same substring.

When used in a map with [value](./value.md) the unpacked value is a concatenation of the bytes of value and suffix

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| String "hello " with suffix "world" | `0x0295ab666068656c6c6f2050776f726c64` | (([type_map](./type_map.md) [value](./value.md) [suffix](./suffix.md) [parse_text](./parse_text.md) [parse_text](./parse_text.md)) (map (u8Text) (u8Text))) | <pre>"hello world"</pre> |
| String "wo" with prefix "hello " and suffix "rld" | `0x03aa95ab666668656c6c6f2020776f30726c64` | (([type_map](./type_map.md) [prefix](./prefix.md) [value](./value.md) [suffix](./suffix.md) [parse_text](./parse_text.md) [parse_text](./parse_text.md) [parse_text](./parse_text.md)) (map (u8Text) (u8Text) (u8Text))) | <pre>"hello world"</pre> |