# IPv4 Analysis
___
**Given**
```shell
IPv4 Address. . . . . . . . . . . : 192.168.137.1
Subnet Mask . . . . . . . . . . . : 255.255.255.0
```
___
**Analysis**
```shell
Network Address . . . . . . . . . : 192.168.137.0
Broadcast Address . . . . . . . . : 192.168.137.255
CIDR Prefix . . . . . . . . . . . : 192.168.137.0/
Host Min. . . . . . . . . . . . . : 192.168.137.0
Host Max. . . . . . . . . . . . . : 192.168.137.255
Available Hosts . . . . . . . . . : 254


Default Router with Integrations:
	Default Gateway . . . . . . . : 192.168.137.1
	DHCP Server . . . . . . . . . : 192.168.137.1
	DNS Server. . . . . . . . . . : 192.168.137.1
```
## Details
### CIDR Prefix
Subnet mask BIN: `11111111.11111111.11111111.00000000`
$2^{32-numOfNetBits}$ = $2^{24}$
### Available Hosts
Subnet mask BIN: `11111111.11111111.11111111.00000000`
- $2^{32-numOfHostBits}-2$
- -2: Broadcast address (255), Network Address (0)
### Subnetting
- Reallocate portion of host bits to subnet bits