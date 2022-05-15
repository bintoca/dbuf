## type_stream_merge

- Begins a variable length scope
- Used to compose the type of a value whose length is not known at the start
- The value will be streamed in known length chunks but considered one value at completion
- Position within the scope is meaningful forming a compact grammar
- The first Item serves as a field identifier when nested in a [`type_struct`](type_struct.md)
- The last Item determines its parse operation during iterations of a [`bind`](bind.md)
- Any middle Items add meta attributes to the type
- [`bind`](bind.md) parse operation: collection_stream