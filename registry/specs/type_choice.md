## type_choice

- Begins a variable length scope
- Used to compose a set of types that can be selected by integer index (also called a sum type)
- During a [`bind`](bind.md), one varint is consumed for the selection and parsing proceeds according to the selected type
- A selection index larger than the length throws [`error_invalid_choice_index`](error_invalid_choice_index.md)