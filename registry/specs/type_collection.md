## type_collection

- Begins a variable length scope
- Used to compose the type of a collection
- Position within the scope is meaningful forming a compact grammar
- The first Item serves as a field identifier when nested in a [`type_struct`](type_struct.md)
- The last Item determines its parse operation during a [`bind`](bind.md)
- Any middle Items add meta attributes to the type
- During a [`bind`](bind.md), one varint is consumed for the length of the collection and its parse operation is run for that many iterations
- The length is biased by one, a zero value means length of one, so empty collections are not allowed
- When nested in a [`type_struct`](type_struct.md) it implies a collection of the parent struct in a column oriented format
- When nested in a [`type_wrap`](type_wrap.md) it implies a collection as the entity value of the field