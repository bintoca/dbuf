## type_wrap

- Begins a variable length scope
- Used to compose a type with various attributes
- Position within the scope is meaningful forming a compact grammar
- The first Item serves as a field identifier when nested in a [`type_struct`](type_struct.md)
- The last Item determines its parse operation during a [`bind`](bind.md)
- Any middle Items add meta attributes to the type