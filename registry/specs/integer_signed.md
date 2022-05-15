## integer_signed

- [`bind`](bind.md) parse operation: varint
- Uses [ZigZag encoding](https://developers.google.com/protocol-buffers/docs/encoding)
- If parse operation is changed to block_size or block_variable, uses two's complement encoding