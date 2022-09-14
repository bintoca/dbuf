## type_choice_bit

- Begins a variable length scope
- Used to compose a set of types that can be selected by integer index (also called a sum type)
- [`bind`](bind.md) parse operation: choice_bit_size
- A selection index larger than the length throws [`error_invalid_choice_index`](error_invalid_choice_index.md)