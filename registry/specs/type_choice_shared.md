## type_choice_shared

ID: 11

Defines a list of options that can be selected by an index.

Functions nearly identically to [type_choice](./type_choice.md) except the options can interact with [type_choice_select](./type_choice_select.md) to create recursive structures.

Consumes one varint "x"

If x equals zero, consume one varint "y", then consume one symbol specifying the type of options to follow, then consume one varint specifying the number of options to follow offset by one, then consume the options, then consume y symbols as additional options.

If x is not zero, consume x symbols as the options.

The values for number of options use offsets so that the minimum number of options is one. This is to avoid ambiguities in the meaning of a choice with zero options.

When encountered in the parsing of a data component: If number of options equals one, consumes zero bits and selects the single option, otherwise consumes the least number of bits that can represent the number of options. The value consumed is a zero based index into the options. If the index is greater than the index of the last option, the last option is selected. Then the list is pushed on to the shared choice stack, which is subsequently poped after the data component rules of the selected option have been executed.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Index greater than the number of options | `0x18b3954561fc00` | (([type_array](./type_array.md) ([type_choice_shared](./type_choice_shared.md) [value](./value.md) [parse_varint](./parse_varint.md) ([parse_bit_size](./parse_bit_size.md) 7))) (array (choice 3 120))) | <pre>[120]</pre> |
| Recursive array | `0x8b112148c01894` | (([type_choice_shared](./type_choice_shared.md) ([type_array](./type_array.md) ([type_choice](./type_choice.md) [parse_varint](./parse_varint.md) ([type_choice_select](./type_choice_select.md) 0)))) (choice 0 (array (choice 1 (choice_select (array (choice 0 5))))))) | <pre>[[5]]</pre> |
| Recursive map | `0x8b20195218c08c142c` | (([type_choice_shared](./type_choice_shared.md) ([type_map](./type_map.md) [value](./value.md) ([type_choice](./type_choice.md) ([type_choice_select](./type_choice_select.md) 0) ([type_choice_select](./type_choice_select.md) 1))) [parse_varint](./parse_varint.md)) (choice 0 (map (choice 0 (choice_select (map (choice 1 (choice_select 6)))))))) | <pre>{"value":{"value":6}}</pre> |
| Array of unsigned integer with options sharing a common type | `0x18b01424569214` | (([type_array](./type_array.md) ([type_choice_shared](./type_choice_shared.md) (([type_array](./type_array.md) [parse_varint](./parse_varint.md)) (array 4 5 6)) [describe_no_value](./describe_no_value.md))) (array (choice 1))) | <pre>[5]</pre> |