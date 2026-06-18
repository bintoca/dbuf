# DBUF Protocol Design Decisions



## Transport Layer

QUIC is a modern transport layer with many advanced features. DBUF aims to take full advantage of QUIC's capabilities while remaining adaptable to other transports.

Alternative transport layers may be suitable if they share the following general characteristics of QUIC.

- A connection can encompass multiple streams.
- Streams can be bidirectional or unidirectional.
- Unreliable datagrams are supported.
- An error code can be transmitted for a stream that fails to send its complete payload.
- Cryptographic keying material can be synthesized from the underlying secure connection.


## Framing

DBUF encoding is length prefixed so the protocol can be constructed with pure DBUF items without an additional framing layer. Extensibility is provided by registry symbols rather than frame types.

## Header Store

Header compression is achieved with a simple dictionary where each dictionary entry can represent more that multiple headers.

Simpler to implement than HTTP3 QPACK with competitive compression ratios for most common scenarios.

Direct integration with authentication, the most common reuse of header data is expected to be authentication. Headers formatted as DBUF items are straightforward to consume in digital signature schemes.

## Addressing

DBUF addresses are just arrays of DBUF items. Registry symbols provide standardized elements within the array.

In contrast to URLs, they don't need one defacto text representation, any way of conveying the DBUF basic data types can be used in user interfaces.

## Errors

Standard errors can be established with registry symbols.

For errors that happen mid-stream, transmitting the error on a different stream, helps make an additional framing layer not necessary.

## Authentication

No shared secrets, digital signature based.

TLS Exporters avoid additional round trip to get a nonce, and avoids tokens that can be used outside the current connection.

Public keys stored on identity setup, referred to by short id, not transferred in authentication. Likely a needed space savings for larger key sizes of post-quantum algorithms.

Recovery mechanism for an identity with multiple authentication keys not specified yet but being worked on.