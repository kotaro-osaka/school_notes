# DHCP
___
> Dynamic Host Configuration Protocol
- Provides `IPv4 address`, `Subnet Mask`, `Standard Gateway IP address`, `DHCP Server IP address`, `DNS Server address`, *other config info*
- Operates on UDP protocol
- Ports: `67`(Source) // `68`(Destination)
- DHCPv4: `IPv4`
- DHCPv6: `IPv6`
## Process
1. **Discover**
	1. Device connects to network
	2. Device sends broadcast message `DHCP Discover`
2. **Offer**
	1. DHCP server(s) on local net respond with `DHCP Offer` message
	2. Message contains `IP address`, `Subnet mask`, `Default gateway`, `DNS server address`
3. **Request**
	1. Device selects one offer
	2. Device sends `DHCP Request` message to server to confirm choice
4. **Acknowledge**
	1. DHCP server sends `DHCP Acknowledge` message confirming IP address assignment to device
	2. Additional information `lease duration`, `...`
5. **Configuration**
	1. Device configures network interface with provided configuration information & parameters
6. **Renewal**
	1. Device periodically attempts to renew lease on IP address
	2. Device contacts DHCP server before lease expiration time
7. **Release**
	1. On device disconnect from network / IP address not needed any longer
	2. Device sends `DHCP Release` message to inform server that IP address can be reclaimed & reused
## DHCP pool
- Table/List that holds...
- available IP addresses in pool
- lease info (duration, start/end time
- client identifier (MAC, other client specific info))
- other config params(subnet mask, default gateway, etc.) kept in Router's RAM