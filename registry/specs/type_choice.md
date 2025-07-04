## type_choice

ID: 2

Defines a list of options that can be selected by an index.

Consumes one varint "x"

If x equals zero, consume one varint "y", then consume one symbol specifying the type of options to follow, then consume one varint specifying the number of options to follow offset by one, then consume the options, then consume y symbols as additional options.

If x is not zero, consume x plus one symbols as the options.

The values for number of options use offsets so that the minimum number of options is one. This is to avoid ambiguities in the meaning of a choice with zero options.

When encountered in the parsing of a data component: Consumes the least number of bits that can represent the number of options. The value consumed is a zero based index into the options. If the index is greater than the index of the last option, the last option is selected.

### Examples

| Description | Binary | S-expression | Unpacked |
|----|----|----|----|
| Array of integers with different sizes | `0x1215258f25a71000` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) ([parse_bit_size](./parse_bit_size.md) 3) ([parse_bit_size](./parse_bit_size.md) 16))) (array (choice 0 5) (choice 1 20000))) | <pre>[5,20000]</pre> |
| Index greater than the number of options | `0x122954561fc0` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) [value](./value.md) [parse_varint](./parse_varint.md) ([parse_bit_size](./parse_bit_size.md) 7))) (array (choice 3 120))) | <pre>[120]</pre> |
| Array of unsigned integers with options sharing a common type (x equals zero pattern in above specs) | `0x12014245692140` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) (([type_array](./type_array.md) [parse_varint](./parse_varint.md)) (array 4 5 6)) [describe_no_value](./describe_no_value.md))) (array (choice 1))) | <pre>[5]</pre> |