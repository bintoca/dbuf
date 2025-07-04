## describe_no_value

ID: 18

Used as a placeholder for an empty value.

When used in a [type_map](./type_map.md) preserves the key's presence, in contrast to [nonexistent](./nonexistent.md) which implies the key is absent.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Empty value | `0x01c04692` | (([type_map](./type_map.md) [denominator](./denominator.md) [describe_no_value](./describe_no_value.md)) (map)) | <pre>{"denominator":"describe_no_value"}</pre> |
| Empty value with error as the reason it is empty | `0x01c0460192a0` | (([type_map](./type_map.md) [denominator](./denominator.md) ([type_map](./type_map.md) [describe_no_value](./describe_no_value.md) [error](./error.md))) (map (map))) | <pre>{"denominator":{"describe_no_value":"error"}}</pre> |