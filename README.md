# DBUF (Dense Binary Universal Format)

A serialization format and wire protocol for high performance self-describing data.

- [Codec](codec.md) - Serialization rules designed around entropy. More frequently used symbols use less bits.

- [Registry](./registry/README.md) - Central list of symbols for describing data structures, types, execution, protocol interactions, etc.

- [Execution](execution.md) - Semantics for computation, errors, etc.

- Coming Soon - data store functionality, addressing, identity, access control, queries, indexing, etc.

## Philosophy

Software applications have evolved with relatively low interoperability. While standards for data and interface description do exist, their usage is highly fragmented. DBUF seeks to overcome the obstacles to wider standards adoption. 

High performance at every level. DBUF aims to improve speed across all facets of the software lifecycle including fast parsers, fast interpreters, fast JIT compiling, potential for deep optimizations including influencing hardware design, fast IO (network and disk), fast adaptation to changing requirements.

The above goals guide the design towards a self-describing binary format. In comparison, a self-describing text format like JSON-LD has too much overhead and a non-self-describing binary format like Protocol Buffers has too much out of band coordination.

The data types of serialization formats have traditionally been the lowest common denominator of types that exist across all programming languages. DBUF has a more powerful type system that can serve as the basis for a new family of programming languages and data stores while still being usable from existing languages.

The flexibility of the format and type system presents serveral challenges when building an implementation but it also creates opportunities for new kinds of adaptive systems. For example, a data store could re-compile itself based on the data it has or is configured to accept.

## Reference Implementation

[bintoca lib repo](https://github.com/bintoca/lib)

## License
Apache-2.0 WITH LLVM-exception