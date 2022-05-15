## IEEE_754_binary

- [`bind`](bind.md) parse operation: block_size with default size: 1
- Base 10 floating point numbers conforming to IEEE 754 standard
- Encoding varies by block size or bit size
  - Block size 1 or bit size <=32 - decimal32
  - Block size 2 or bit size <=64 - decimal64
  - Block size 3-4 or bit size <=128 - decimal128
- All sizes use DPD (densely packed decimal) encoding