# DBUF (Dense Binary Universal Format)

DBUF is a data specification with the ambitious goal of unifying programming languages, databases and network protocols. It is a self-describing binary format where symbols compose to form a sophisticated type system.

The core benefit of DBUF is optimization. Data types can be fine tuned for minimal size or high processing throughput, making it suitable for a wide range of use cases including storage, interchange and in-memory structures.

DBUF's expressiveness also gives it great potential for interoperability. A public registry of symbols provides extensibility to describe any new type of data, while the core structural rules will remain fixed for permanent backwards compatability.

- [Codec](codec.md)

- [Symbol Registry](./registry/README.md)

## Reference Implementation

[bintoca lib repo](https://github.com/bintoca/lib)

## License
Apache-2.0 WITH LLVM-exception