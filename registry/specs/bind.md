## bind

- Begins a 2 Item Scope
- The first Item is a data type that describes how to continue parsing and construct the second Item
- The composition of the first Item translates into a composition of the following parse operations:
  - varint - consumes one varint
  - item - parses one Item by default rules
  - block_size - consumes a fixed number of blocks
  - block_variable - consumes one varint for number of blocks to consume, bias by 1, no zero lengths
  - bit_size - consumes a fixed number of bits from a non-varint block
  - bit_variable - consumes one varint for number of bits to consume, bias by 1, no zero lengths
  - text_plain - implicitly begins a variable length Scope using the [text symbol list](../text.md) and plain text rules
  - text_rich - implicitly begins a variable length Scope using the [text symbol list](../text.md) and rich text rules
  - collection - consumes one varint for the number of iterations, bias by 1, no zero lengths
  - collection_stream - iterates repeatedly, consumes one varint after each iteration, stops on zero value, continues on non-zero value
  - choice - consumes one varint for choice selection, continues according to choice
  - varint_plus_block - consumes one varint and one block
  - none - consumes nothing
- When a nested bind appears in the compostion of the first Item, its parse operation is 'item'