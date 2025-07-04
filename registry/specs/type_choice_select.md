## type_choice_select

ID: 12

Defines the selection of an option in an enclosing [type_choice_shared](./type_choice_shared.md). Useful for creating recursive structures.

Consumes one varint specifying a zero based index.

When encountered in the parsing of a data component: Selects an option by the specified index from the top item of the shared choice stack. If the selected option is a [type_choice_select](./type_choice_select.md) use its index to select from the next item down in the shared choice stack. If this iteration continues past the bottom of the shared choice stack, the selection is interpreted as [nonexistent](./nonexistent.md)

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Recursive map | `0x8b20195218c08c142c` | (([type_choice_shared](./type_choice_shared.md) ([type_map](./type_map.md) [value](./value.md) ([type_choice](./type_choice.md) ([type_choice_select](./type_choice_select.md) 0) ([type_choice_select](./type_choice_select.md) 1))) [parse_varint](./parse_varint.md)) (choice 0 (map (choice 0 (choice_select (map (choice 1 (choice_select 6)))))))) | <pre>{"value":{"value":6}}</pre> |
| Recursive shared | `0x8b201958b201c0468c18c14180` | (([type_choice_shared](./type_choice_shared.md) ([type_map](./type_map.md) [value](./value.md) ([type_choice_shared](./type_choice_shared.md) ([type_map](./type_map.md) [denominator](./denominator.md) ([type_choice_select](./type_choice_select.md) 1)) ([type_choice_select](./type_choice_select.md) 1))) [parse_varint](./parse_varint.md)) (choice 0 (map (choice 0 (map (choice_select 6)))))) | <pre>{"value":{"denominator":6}}</pre> |
| Missing shared | `0x01c0468c10` | (([type_map](./type_map.md) [denominator](./denominator.md) ([type_choice_select](./type_choice_select.md) 1)) (map (choice_select))) | <pre>{}</pre> |