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
**ARP (Address Resolution Protocol)**
- Löst IP-Adresse in MAC-Adresse auf (Layer 3 → Layer 2)
- Sendet Broadcast-Anfrage um Host mit jeweiligen IP zu finden

