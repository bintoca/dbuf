# DBUF Registry

The registry is a central list of symbols with precise specifications. An initial set of symbols will define the core semantics of DBUF required for a parser implementation. After that, symbols will continue to be added but only with semantics that compose with the initial symbols. This ensures forward compatibility of parsers and consistency of implementations.

Symbols will be assigned a numeric id based on their expected frequency of use with the most frequent assigned to the lowest numbers. Gaps in the id sequence will exist as reserved space for high importance symbols defined in the future. The packed varints defined in the [DBUF codec](../codec.md) have sizes in multiples of 3 bits. This makes the average density of the DBUF format dependent on the careful allocation of symbols, particularly in the ranges 0-7, 8-63 and 64-511.

- [ID Index](index.md) - Subject to change until core semantics are settled

## Text

Text is represented by a separate list that contains all unicode code points plus a few extra control symbols. The ASCII range is remapped for improved density. The codec semantics will have well defined rules for when to interpret a varint as text or a regular symbol.

- [Text Spec](text.md) - Subject to change until core semantics are settled