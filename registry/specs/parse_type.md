## parse_type

ID: 14

Defines a parsing context that begins with a type definition followed by data conforming to that type.

The type component begins in [parse mode any](../../codec.md) and follows any nested semantics of its parsed symbol. Next the resolved parse mode of the type component is used to parse the data component.

A DBUF stream is an implicit [parse_type](./parse_type.md). The initial symbol is ommitted but the end of the [parse_type](./parse_type.md)'s scope represents the end of the DBUF stream. If a sequence of data is desired, it must be explicitly defined as such inside the implicit [parse_type](./parse_type.md)

### Examples

Integer: ([parse_type](./parse_type.md) [parse_varint](./parse_varint.md) 3)