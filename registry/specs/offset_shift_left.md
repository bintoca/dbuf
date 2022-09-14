## offset_shift_left

- [`bind`](bind.md) parse operation: varint
- When composed in a nested [`bind`](bind.md), bound values will be interpreted by performing a binary shift left by the number of bits + 1 of the child value
- Useful for reduced precision floating point numbers encoded in varint blocks 