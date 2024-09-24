---
tags:
  - osi_layers
  - osi_sublayers
---
# OSI Model
___
> Open Systems Interconnection
- Conceptual framework
- Standardizes functions of telecommunication or computing system into 7 layers
- Each layer has specific responsibilities and interacts with adjacent layers
## Layers
___
### 7. Application Layer
- Provides network services directly to end-user app
- Enables communication between user apps and network
- Includes protocols for services
	- Email ([[00 - BSN/1 - glossary/1.1 - protocols/mailing protocols/smtp|SMTP]])
	- File transfer ([[00 - BSN/1 - glossary/1.1 - protocols/ftp|FTP]])
	- Web browsing ([[00 - BSN/1 - glossary/1.1 - protocols/http|HTTP]])
	- Domain name resolution ([[00 - BSN/1 - glossary/1.1 - protocols/dns|DNS]])
### 6. Presentation Layer
- Handles data formatting, encryption & compression for efficient transmission
- Translates data into format understandable & processable for application layer
### 5. Session Layer
- Responsible for session initialization, synchronization & maintenance
- Establishes, manages & terminates connections between apps
- Dialogue control
- Supports Multiple sessions between apps
### 4. Transport Layer
- Ensures reliable end-to-end communication between hosts
- Provides segmentation, error recovery, flow control & reassembly of data mechanisms
- [[00 - BSN/1 - glossary/1.1 - protocols/tcp|TCP]], [[00 - BSN/1 - glossary/1.1 - protocols/udp|UDP]]
### 3. Network Layer
- Manages routing of packets from source to destination across nodes
- Determines best path for data transmission based on network conditions and addressing
- [[00 - BSN/1 - glossary/1.2 - addressing/ipv6/ipv6|IPv6]], [[00 - BSN/1 - glossary/1.1 - protocols/icmp|ICMP]]
### 2. Data Link Layer
- Handles reliable transmission of frames between adjacent nodes over physical link
- Provides flow control, error detection & correction
- Sublayers: [[#LLC]], [[#MAC]]
### 1. Physical Layer
- Responsible for transmitting raw data bits over physical medium (cables, wires, fiber optics)
- Defines characteristics: Voltage levels, cable types, data rates
- Concerned with mechanical, electrical & procedural aspects of transmitting data
## Sublayers
___
### Data Link Layer
#### LLC
> Logical Link Control
- Provides error control, flow control & frame synchronization services to network layer
- Ensures error-free data delivery between devices on same network segment regardless of network medium
- Protocol-independent
	- Works with various network protocols
	- Adaptable to different network tech
#### MAC
> Media Access Control
> MAC address == Physical address == Hardware address
- Controls access to physical network medium
- Manages transmission of frames between devices on same network segment
- MAC protocols determine how devices contend for access to network medium, handle collisions & control flow of data
## OSI Model with reference to [[00 - BSN/1 - glossary/1.0 - misc/encapsulation|Encapsulation and Decapsulation]]
___
![[osi_encapsulation.png|750]]
