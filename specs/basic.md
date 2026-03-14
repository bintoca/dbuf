# Basic Encoding

The DBUF basic format is a type-length-value structure designed for compactness and low complexity of encoding/decoding.

## Type Prefix

The most significant 3 bits of a byte define the type of DBUF item. The 8 possible values are:

- 0 - unsigned integer
- 1 - unsigned integer bytes
- 2 - utf8
- 3 - bytes
- 4 - array - contains nested DBUF items
- 5 - map - contains nested DBUF items interpreted as key-value pairs
- 6 - registry symbol - IDs from the [Registry](./registry/README.md)
- 7 - registry symbol bytes


## Length and Value

The remaining 5 bits of a byte form a variable length integer (varint). For type 0 and 6 the varint is the value. For all other types the varint is the length of the value in bytes.

Varint encoding rules of the 5 bits (32 possible values):

- 0-23 - the value itself, no additional bytes
- 24-27 - combine the 2 least significant bits with one additional byte to form a 10-bit unsigned integer
- 28-29 - combine the 1 least significant bit with two additional bytes to form a 17-bit unsigned integer
- 30 - take 3 additional bytes as a 24-bit unsigned integer
- 31 - take 4 additional bytes as a 32-bit unsigned integer


Additional bytes are in big endian byte order