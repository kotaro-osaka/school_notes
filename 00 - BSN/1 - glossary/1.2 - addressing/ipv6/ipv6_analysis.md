# IPv6 Analysis
___
## Without Subnetting
**Given**
```shell
IPv6 Address. . . . . . . . . . . : 2019:abcd:0123:1200:0000:0000:0000:0000/64
```
___
**Analysis**
```shell
Network Prefix. . . . . . . . . . : 2019:abcd:0123:1200
Interface ID. . . . . . . . . . . : 0000:0000:0000:0000
```
### Details
- `/64` Network prefix is immutable
## With Subnetting
**Given**
```shell
IPv6 Address. . . . . . . . . . . : 2019:abcd:0123:1200:0000:0000:0000:0000/56
IPv6 Address (short). . . . . . . : 2019:abcd:123:1200::/56
```
___
**Analysis**
```shell
GLobal Routing Prefix . . . . . . : 2019:abcd:0123:12
Subnet Min. . . . . . . . . . . . : 1200::/56
Subnet Max. . . . . . . . . . . . : 12ff::/56
Max Num of Subnets. . . . . . . . : 2^8 (64-56=8)
Interface ID. . . . . . . . . . . : 0000:0000:0000:0000
```
### Details
- <`/64` Subnetting possible for prefix smaller than 64















[[00 - BSN/1 - glossary/1.2 - addressing/ipv6/ipv6_address_types|more]]