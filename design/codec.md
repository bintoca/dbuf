# DBUF Codec Design Decisions

## Self Describing Data

The cornerstone of collaboration is exchanging data. 



## Symbol Registry

In the pursuit of interoperability, there is a clear need to uniquely identify concepts. DBUF accommodates this with a global symbol list. Symbols are encoded as integers but are a distinct data type separate from integers. 

Encoding as integers provides a compact representation even in the most minimal implementations. In contrast, RDF subject and predicate URLs are much larger and typically require another form of compression for practical usage.

Having one global registry creates some centralization but it's an opportunity to create a space to come together and collaborate.

## Varints