# Basic Encoding

The DBUF basic format is a type-length-value structure designed for compactness and low complexity of encoding/decoding.

## Type Prefix

The most significant 3 bits of a byte define the type of DBUF item. The 8 possible values are:

- 0 - integer
- 1 - float
- 2 - text - utf8 encoded
- 3 - bytes
- 4 - array - contains nested DBUF items
- 5 - map - contains nested DBUF items interpreted as key-value pairs
- 6 - registry symbol - IDs from the [Registry](./registry/README.md)
- 7 - unsigned integer - max 32-bit


## Length and Value

The remaining 5 bits of a byte form a variable length integer (varint). For type 6 and 7 the varint is the value. For all other types the varint is the length of the value in bytes.

Varint encoding rules of the 5 bits (32 possible values):

- 0-23 - the value itself, no additional bytes
- 24-27 - combine the 2 least significant bits with one additional byte to form a 10-bit unsigned integer
- 28-29 - combine the 1 least significant bit with two additional bytes to form a 17-bit unsigned integer
- 30 - take 3 additional bytes as a 24-bit unsigned integer
- 31 - take 4 additional bytes as a 32-bit unsigned integer


Additional bytes are in big endian byte order

## Integer Type - 0

Integers are encoded as a two's complement byte array with big endian byte order.

A zero length byte array is interpreted as -1.

## Float Type - 1

Float encoding is based on the length of the value. All variations are big endian byte order.

- A zero length value is interpreted as NaN.
- A 1 byte value is interpreted as IEE754_binary16 with an implied second byte of 0.
- A 2 byte value is interpreted as IEE754_binary16.
- A 3 byte value is interpreted as IEE754_binary32 with an implied fourth byte of 0.
- A 4 byte value is interpreted as IEE754_binary32.
- A 5 byte value is interpreted as IEE754_binary64 with implied sixth, seventh and eighth bytes of 0.
- A 6 byte value is interpreted as IEE754_binary64 with implied seventh and eighth bytes of 0.
- A 7 byte value is interpreted as IEE754_binary64 with an implied eighth byte of 0.
- A 8 byte value is interpreted as IEE754_binary64.
- All other lengths are reserved for future specification.
