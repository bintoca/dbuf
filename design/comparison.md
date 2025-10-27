# DBUF compared to other technologies

## JSON

#### Types

JSON has limited data types. Numbers do not have a distinction between integers, binary floats and decimals. Map keys must be strings. There is no official standard for dates or binary data. All values are encoded as strings.

DBUF has a composable type system that covers far more data types. Flexible binary encodings achieve higher performance.

#### Layout

JSON has a basic verbose layout. In an array of similar maps, each map repeats its keys. External compression is needed to reduce the impact of this verbosity.

DBUF describes structures in a way that reduces redundancies (semantic compression).

#### Extensibility 

JSON has no extensibility at the syntax level. This was actually key to its success since it prevented fragmentation of implementations. Unfortunately it also prevents adding common data types and other semantics must be defined at a higher level where there is significant fragmentation. 

DBUF has a stable set of core semantics with no versioning. Extensibility is achieved through symbols, making evolution more predictable while maintaining low level compatibility. 

## XML

#### Types

XML has more standardized data types than JSON but they are still based on string encodings.

DBUF has a composable type system that can create more adaptive descriptions of data. Flexible binary encodings achieve higher performance.

#### Layout

XML has a verbose nested layout. In an array of similar maps, each map repeats its keys. Element names are repeated in opening and closing tags. External compression is needed to reduce the impact of this verbosity. The separation of attributes and child elements creates a mismatch with other type systems.

DBUF describes structures in a way that reduces redundancies (semantic compression). All structures logically unpack to maps and arrays, which aligns better with other type systems.

#### Extensibility 

XML doc types and namespaces have proved cumbersome and prone to fragmentation.

DBUF has a stable set of core semantics with no versioning. Extensibility is achieved through symbols, making evolution more predictable while maintaining low level compatibility.

## RDF

#### Types

RDF uses XML Schema Definition data types which are based on string encodings. The main structural element is a triple which is an awkward fit for representing arrays. Blank nodes are also overhead needed for nesting.

DBUF has a composable type system with more natural descriptions of data as map and arrays. Flexible binary encodings achieve higher performance.

#### Layout

RDF is an abstract syntax with no official encoding. Various encodings have been implemented leading to significant fragmentation. Subjects and predicates defined as URLs are large values needing compression schemes for practical usage.

DBUF has a set of encoding rules that ensure varied implementations can share more semantics. Integer symbols are compact without additional compression schemes.

#### Extensibility 

RDF has high extensibility through the use of URLs, but it is so generic that it leads to a more fragmented rather than cohesive ecosystem.

DBUF provides the same amount of extensibility through its symbol registry, but with semantics that can better guide the ecosystem towards cooperation. 

## CSV

#### Types

CSV has no official data types. All values are strings with imprecise conventions for interpretation. 

DBUF has a composable type system that can create more precise and standardized descriptions of data. Flexible binary encodings achieve higher performance.

#### Layout

CSV is delimited text forming rows and columns. Its perceived simplicity often leads to bugs with escaping and encoding.

DBUF describes structures in a way that reduces redundancies (semantic compression). Its precise rules encourage well tested libraries and consistent implementations.

#### Extensibility

CSV is very flexible since it could be used with any string, but it has no mechanism for coordination more details semantics.

DBUF provides coordinated extensibility through is symbol registry.

## CBOR 

## ASN.1

## Protocol Buffers

## Cap'n Proto

## Object Identifiers