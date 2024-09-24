# TCP
___
> Transmission Control Protocol
> [[00 - BSN/1 - glossary/1.0 - misc/encapsulation#TCP Segment|more]]
- Reliable connection-oriented communication between devices on network
- **Reliability**: Acknowledges received packets and retransmitting if necessary
- **Ordered Delivery**: Ensures data packets arrive in correct order
- **Flow Control**: Adjusts transmission rate based on receiver’s ability to process data
- **Connection Establishment & Termination**
	- Three-way handshake for connection setup
	- Four-way handshake for connection termination
- Use Cases: Guaranteed delivery requirement, ordered data transmission (web browsing, email, file transfer)
- ![[tcp_header.png]]
- 