## TAI_seconds

- [`bind`](bind.md) parse operation: block_size with default size: 1
- SI atomic seconds according to TAI standard
- Start of epoch is aligned with GPS (January 6, 1980)
- Defaults to a 32-bit integer unsigned

TAI is chosen as the representation for integer timestamps to reduce the proliferation of time scales. Implementations will need a leap second table to convert to UTC. The ITU is scheduled to debate the leap seconds standard in 2023. If leap seconds are discontinued a static leap second table will suffice.

The GPS epoch is chosen to make it easier to find discrepancies in implementations incorrectly using a POSIX timestamp relative to 1970.