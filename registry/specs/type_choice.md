## type_choice

ID: 4

Defines a list of options that can be nested in other structures.

Consumes one varint specifying the number of options to parse with [parse mode any](../../codec.md)

The number of options is offset by two, meaning a literal value of zero equals two options and therefore the lowest number of options is two. This is to avoid ambiguities in the meaning of a choice with zero or one options.

### Examples

| Description | Binary | S-expression |
|----|----|----|
| Array of integers with different sizes | `0x3406268f25a71000` | (([type_array](./type_array.md) ([type_choice](./type_choice.md) ([parse_bit_size](./parse_bit_size.md) 3) ([parse_bit_size](./parse_bit_size.md) 16))) ([array](../node_types/array.md) ([choice](../node_types/choice.md) 0 5) ([choice](../node_types/choice.md) 1 20000))) |