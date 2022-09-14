## type_choice

- Begins a variable length scope
- Used to compose a set of types that can be selected by integer index (also called a sum type)
- [`bind`](bind.md) parse operation: choice
- A selection index larger than the length throws [`error_invalid_choice_index`](error_invalid_choice_index.md)
- If the parse operation of the last item in the scope is one of the following, the choice selection will also serve as the parse value, offset by the number of choices.
  - bit_variable
  - block_variable
  - item
  - text
  - varint
  - varint_plus_block
- If nested in a [`type_array`](type_array.md) and the parse operation of the selection is item then the parse operation becomes none.
- An empty scope represents [`placeholder`](placeholder.md)