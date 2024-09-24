# OSPF
___
> Open Shortest Path First
>> *Orientiert sich an Statusinformationen der Links in zutreffenden Paths*
- Link-State Routing
- **Routing metric**: Link States

1. Gathers link state info from available routers
2. Constructs topology map of network (routing table)
(→ [[#LSA]])

- Detects changes in topology (link failures)
- Algorithm calculates shortest path (→ loop-free)

## RIB
> Routing Information Base
- Database of routing information
- Used to calculate loop-free routes
## LSA
> Link State Advertisement
- Exchanged to build map of network topology
## DR / BDR
> (Backup) Designated Router
- Elected to reduce number of adjacencies & prevent loops
- Used in OSPF multi-access networks
## LFA
> Loop-Free Alternate
- Calculated backup paths
- Provides fast rerouting in case of link failures
- Ensures traffic forwarding without loops

- Widely used in large enterprise networks
## Header
![[../../../0 - res/ospf_packets.png]]