# IPv6 Aufgaben
___
## 1. Erkennung IPv4 vs. IPv6
**Network Layer:**
Host erkennt anhand des **Version-Feldes im IP-Header** (ersten 4 Bits)
- `0100` = `4` → IPv4
- `0110` = `6` → IPv6

**Data-Link Layer:**
**EtherType** im Frame-Header signalisiert verwendete Version
- `0x0800` → IPv4
- `0x86DD` → IPv6

## 2. Adresslänge
- IPv4: 32 Bit
- IPv6: 128 Bit

## ARP-Äquivalent
**IPv4: ARP (Address Resolution Protocol)**
- Löst IP-Adresse in MAC-Adresse auf (Layer 3 → Layer 2)
- Sendet Broadcast-Anfrage um Host mit jeweiligen IP zu finden

**IPv6: NDP (Neighbor Discovery Protocol)**
- Ersetzt *ARP*, *ICMP Router Discovery*, *ICMP Redirect*

**ICMPv6-Nachrichtentypen von NDP:**

| Typ | Name                       | Funktion                                                             |
| --- | -------------------------- | -------------------------------------------------------------------- |
| 133 | Router Solicitation (RS)   | Host sucht nach Router                                               |
| 134 | Router Advertisement (RA)  | Router antwortet periodisch oder auf RS mit Präfix MTU, Gateway-Info |
| 135 | Neighbor Solicitation (NS) | Ersetzt ARP-Request -                                                |
