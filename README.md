# DBUF (Dense Binary Universal Format)

DBUF is a data specification forming the basis of a community of software and tools. It is a self-describing binary format where symbols compose to form a sophisticated type system.

## Ideals

- **Enable new ways of working together** - Fragmentation is a chronic barrier in the pursuit of software that meets people's needs. Creating interoperable foundations can unlock new freedoms and creativity.

- **Long term approach to design** - Rigorous study of prior art focused on identifying fundamental paradigms that will not change. Avoid expedient shortcuts based on current technology fashions or product launch timelines.   

- **Maximum potential for optimization** - Not everyone cares about performance, but to build the strongest ecosystem, the coalition must include those that do care about performance. Careful design around progressive optimization is key so that optimal and non-optimal solutions can interoperate. High optimization is also necessary to create cost incentives to displace legacy technologies.

## Design

- [Codec Design Decisions](./design/codec.md)

- [Comparisons to other technologies](./design/comparison.md)

- [Protocol Design Decisions](./design/protocol.md)

## Specifications

- [Basic Encoding](./specs/basic.md)

- [Packed Encoding](./specs/packed.md)

- [Symbol Registry](./specs/registry/README.md)

- [Application Protocol](./specs/protocol.md)

## Contributing

No formal process yet. Say hi, use the github discussions and issues in this repo.

## Reference Implementations

[lib repo](https://github.com/bintoca/lib) - prototyping of the packed encoding

[demo repo](https://github.com/bintoca/dbuf-demo-go) - proof of concept client/server implementation of DBUF protocol

## License
Apache-2.0 WITH LLVM-exception