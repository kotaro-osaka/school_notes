# RIP
___
> Routing Information Protocol
- Distance-Vector Routing
- **Routing metric**: Hop Count
- TTL (Time-To-Live): Prevents routing loops by limiting number of hops allowed in path (`≥15`)
	- Limited network size
- Prevents incorrect routing information via [[00 - BSN/1 - glossary/1.3 - routing/split_horizon|Split Horizon]], [[00 - BSN/1 - glossary/1.3 - routing/route_poisoning|route poisoning]] & [[00 - BSN/1 - glossary/1.3 - routing/holddown|holddown]]
- Sends entire routing table to neighbor (30min clock rate)

- [[00 - BSN/1 - glossary/1.1 - protocols/udp|UDP]]
- Port: `520`
- Non-favorable choice compared to [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/eigrp|EIGRP]], [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/ospf|OSPF]], [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/is-is|IS-IS]]
	- Due to scalability & convergence speed limitations
