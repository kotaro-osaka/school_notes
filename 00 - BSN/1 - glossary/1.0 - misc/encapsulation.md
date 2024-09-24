---
tags:
  - encapsulation
  - decapsulation
  - horizontal_communication
  - segment
  - datagram
  - packet
  - frame
  - header
  - tcp
  - udp
---
# Data Encapsulation
___
- Adding information as headers to data when traveling through DOD model layers
- Removing headers by traveling back through the same OSI model layers to unpack data
### Terms
- **Horizontal Communication**: Headers are added and removed on the same OSI Layers
- **Segment**: Transmission via TCP
- **Datagram**: Transmission via UDP
### Process
1. `Message`
2. `TCP Segment` (Message + **TCP** Header) // `UDP Datagram` (Message + **UDP** Header)
3. `IP Datagram` (Message + TCP/UDP Header + IP Header)
4. `Frame` (Frame Header + Message + TCP Header + IP Header + Frame Footer)
### Content of Segments
___
#### TCP Segment
> DOD: Application Layer
> [[00 - BSN/1 - glossary/1.1 - protocols/tcp|TCP]]
- `Sequence numbers`: Used for ordering and reassembling segments at receiver
- `Acknowledgement numbers`: Used for acknowledging receipt of data
- `Control flags`: `SYN`, `ACK`, `FIN`, etc., for establishing/managing TCP connection
- `Window size`: Indicates amount of data that can be sent without acknowledgement
- `Checksum`: Calculated by algorithm before sending and on receipt, if identical, no alteration during transport
#### UDP Datagram
> DOD: Application Layer
- `Source port number`: Identifies sending app
- `Desitnation port number`: Identifies receiving app
- `Length`: Specifies length of datagram
- `Checksum`: Calculated by algorithm before sending and on receipt, if identical, no alteration during transport (optional in IPv4, mandatory in IPv6)
- [[00 - BSN/1 - glossary/1.1 - protocols/udp|UDP]]
#### IP Datagram
> DOD: Network Layer
- `Source IP address`: Identifies sender of packet
- `Destination IP address`: Identifies intended recipient of packet
- `TTL (Time-to-Live)`: Limits lifespan of packet in network; Decremented before each hop and discarded if TTL reaches 0
- `Protocol`: Specifies protocol used for encapsulating payload ([[00 - BSN/1 - glossary/1.1 - protocols/tcp|TCP]] / [[00 - BSN/1 - glossary/1.1 - protocols/udp|UDP]] / [[00 - BSN/1 - glossary/1.1 - protocols/icmp|ICMP]])
- `Checksum`: Calculated by algorithm before sending and on receipt, if identical, no alteration during transport
- `Options`: Additional optional fields/parameters
#### Frame
> OSI: Data Link Layer
- `Source MAC address`: Identifies sender’s MAC address
- `Destination MAC address`: Specifies intended recipient’s MAC address
- `Type/Length`: Indicates type of payload or length of payload
- `FCS (Frame Check Sequence)`: Field used for error detection, often achieved through CRC (Cyclic Redundancy Check) checksum
- `Optional`: Depending on data link protocol (Ethernet, WiFi, etc.) may include fields (VLAN tags, Frame Control fields, other protocol-specific info)