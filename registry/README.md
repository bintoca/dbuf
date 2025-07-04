# DBUF Registry

The registry is a public list of symbols with precise specifications. An initial set of symbols will define the core semantics of DBUF required for a parser implementation. After that, symbols will continue to be added but only with semantics that compose with the initial symbols. This ensures forward compatibility of parsers and consistency of implementations.

Symbols will be assigned a numeric id based on their expected frequency of use with the most frequent assigned to the lowest numbers. Gaps in the id sequence will exist as reserved space for high importance symbols defined in the future. The varints defined in the [DBUF codec](../codec.md) have sizes of 3, 6, 13, 20 or 32 bits. Therefore special care is taken for the allocation of symbols, particularly in the lower ranges 0-7, 8-63 and 64-8191.

- [ID Index](index.md) - Subject to change until core semantics are settled