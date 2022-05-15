## IEEE_754_binary

- [`bind`](bind.md) parse operation: block_size with default size: 1
- Base 2 floating point numbers conforming to IEEE 754 standard
- Encoding varies by block size or bit size
  - Block size 1 or bit size <=32 - binary32
  - Block size 2 or bit size <=64 - binary64
  - Block size 3-4 or bit size <=128 - binary128
  - Block size 5-8 or bit size <=256 - binary256