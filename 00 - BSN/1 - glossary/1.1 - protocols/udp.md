# UDP
___
> User Datagram Protocol
- Connectionless, unreliable communication service
- **Connectionless**: No need to establish connection before sending data
- **Unreliable**: Doesn’t guarantee delivery or order of packets
- **Low Overhead**: Lightweight (compared to TCP), suitable for apps where `speed > reliability`
- **No Flow Control**: Sender does not adjust transmission rate based on receiver’s ability to process data ([[00 - BSN/1 - glossary/1.1 - protocols/tcp|TCP]] feature)
- Use Cases: Real-time/near-real-time critical transmission
	- Streaming media, gaming, VoIP, DNS queries
- Apps may implement own mechanisms for reliability & ordering on top of UDP (in-game protocols for reliable delivery of game data)
- ![[udp_header.jpg]]