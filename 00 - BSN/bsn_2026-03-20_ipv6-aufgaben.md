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

## 3. ARP-Äquivalent
**IPv4: ARP (Address Resolution Protocol)**
- Löst IP-Adresse in MAC-Adresse auf (Layer 3 → Layer 2)
- Sendet Broadcast-Anfrage um Host mit jeweiligen IP zu finden

**IPv6: NDP (Neighbor Discovery Protocol)**
- Ersetzt *ARP*, *ICMP Router Discovery*, *ICMP Redirect*
- Verwendet **Solicited-Node Multicast-Adressen**, die sich aus `ff02::1:ff` + letzten 24 Bit der Ziel-IPv6-Adresse zusammensetzten
	- **Bsp.:** Wird nach `fe80::a1d6:ffff:acda:16fd` gesucht, wird `ff02::1:ffda:16fd` gesendet
	- **Nur der Host mit der passenden Adresse muss den Frame verarbeiten - alle anderen verwerfen ihn auf Schicht 2**

**ICMPv6-Nachrichtentypen von NDP:**

| Typ | Name                        | Funktion                                                                                                                                                                                                                                                                   |
| --- | --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 133 | Router Solicitation (RS)    | Host sendet diese Nachricht direkt nach dem Verbindungsaufbau ins Netz, um aktiv nach einem Router zu fragen, statt auf das nächste *RA* zu warten                                                                                                                         |
| 134 | Router Advertisement (RA)   | Router senden diese Nachricht alle `200` Sekunden oder als direkte Antwort auf eine *RS*.<br>Enthält `Netzpräfix`, `MTU` des Links, `Gültigkeitsdauer` der Adressen, `Flags`, die dem Host mitteilen, ob `SLAAC` oder `DHCPv6` zur Autokonfiguration verwendet werden soll |
| 135 | Neighbor Solicitation (NS)  | Ersetzt ARP-Request.<br>“Wer hat diese IPv6-Adresse? Antworte mit deiner MAC.”                                                                                                                                                                                             |
| 136 | Neighbor Advertisement (Na) | Ersetzt ARP-Reply.<br>Angesprochene Host antwortet mit seiner MAC-Adresse direkt an den Absender.                                                                                                                                                                          |
| 137 | Redirect                    | Router sendet diese Nachricht an einen Host, wenn er weiß, dass ein anderer Router im selben Subnetz ein besserer nächster Hop für ein bestimmtes Ziel wäre.<br>Host aktualisiert seinen Routing-Cache.<br>Vermeidet unnötige Umwege & entlastet Router.                   |
**Vergleich ARP vs. NDP**

|                 | ARP                                 | NDP                                                                                       |
| --------------- | ----------------------------------- | ----------------------------------------------------------------------------------------- |
| Protokoll       | Eigenständig (EtherType 0x0806)     | Teil von ICMPv6, in IPv6 integriert                                                       |
| Adressierung    | Broadcast - alle müssen verarbeiten | Solicited-Node Multicast - nur betroffene Hosts                                           |
| Netzlast        | Hoch                                | Deutlich geringer                                                                         |
| Sicherheit      | Keine - anfällig für ARP-Spoofing   | Erweiterbar mit `SEND` (Secure NDP)                                                       |
| Funktionsumfang | Nur MAC-Adressauflösung             | Adressauflösung + Router Discovery + SLAAC + DAD (Duplicate Address Detection) + Redirect |
### Weitere NDP-Funktionen:
#### SLAAC - Stateless Address Autoconfiguration
1. Host empfängt Netzpräfix via *RA*
2. Kombiniert Netzpräfix mit Interface-ID
	=> Fertige IPv6-Adresse ohne DHCP
#### DAD - Duplicate Address Detection
- Bevor ein Host eine selbst konfigurierte Adresse nutzt, sendet er eine *NS*-Nachricht an diese *tentative* Adresse
- Antwort = Konflikt => Adresse wird verworfen
#### Router Discovery
- Host finden automatisch ihre Default-Gateway über RS/RA
- Ohne statische Konfiguration oder DHCPv6

## 4. Netz- & Broadcastadresse für `fe80::a1d6:ffff:ac`