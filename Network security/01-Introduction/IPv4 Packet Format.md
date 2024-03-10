[[13- IPSec]].

![[Screenshot 2024-02-04 at 17.20.49.png]]

- **Version (4 bits)**: Specifies the IP version being used, which is 4 for IPv4.
- **Internet Header Length (IHL) (4 bits)**: Indicates the header length in 32-bit words. The minimum value is 5, which corresponds to a header length of 20 bytes.
- **Type of Service (ToS) (8 bits)**: Specifies how an upper-layer protocol would like a current datagram to be handled, and assigns datagrams a level of importance.
- **Total Length (16 bits)**: Specifies the total length of the packet in bytes, including **==both header and data==**.
- **Identification (16 bits)**: Used for uniquely identifying the group of fragments of a single IP datagram.
- **Flags (3 bits)**: Used to control or identify fragments. It includes:
  - Bit 0: Reserved, must be zero.
  - Bit 1: Don't Fragment (DF).
  - Bit 2: More Fragments (MF).
- **Fragment Offset (13 bits)**: Specifies the offset of a particular fragment relative to the beginning of the original unfragmented IP datagram.
- **Time to Live (TTL) (8 bits)**: Limits the lifespan of a datagram in the network, decreasing by one for each router it passes through.
- **Protocol (8 bits)**: Indicates the protocol used in the data portion of the IP datagram.
- **Header Checksum (16 bits)**: Used for error-checking of the header.
- **Source IP Address (32 bits)**: Specifies the sending node.
- **Destination IP Address (32 bits)**: Specifies the receiving node.
- **Options (Variable)**: Allows for various internet options; this field is optional and can vary in length.
- **Padding (Variable)**: Ensures the IP header is a multiple of 32 bits in length. Padding is used if the Options field is used and not a multiple of 32 bits.
