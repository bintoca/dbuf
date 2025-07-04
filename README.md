# DBUF (Dense Binary Universal Format)

DBUF is a data specification forming the basis of a community of software and tools. It is a self-describing binary format where symbols compose to form a sophisticated type system.

Data types can be fine tuned for minimal size or high processing throughput, making it suitable for a wide range of storage, interchange and in-memory use cases.

DBUF's expressiveness also gives it great potential for interoperability. A public registry of symbols provides extensibility to describe any new type of data, while the core structural rules will remain fixed for permanent backwards compatability.

- [Codec](codec.md)

- [Symbol Registry](./registry/README.md)

## Reference Implementation

[bintoca lib repo](https://github.com/bintoca/lib)

## License
Apache-2.0 WITH LLVM-exception