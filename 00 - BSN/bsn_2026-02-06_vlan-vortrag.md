# VLAN
___
> BSN | 06.02.2026 | Kotaro Osaka
## Einleitung
- VLAN = “Virtual Local Area Network”
- Logische Trennung eines physischen Netzwerks
- Geräte können getrennt werden, wenn am selben Switch
- Struktur, Sicherheit, Übersichtlichkeit
## VLAN-ID
- Regelung von VLAN-Zugehörigkeit über VLAN-ID
- VLAN-ID = eindeutige Nummer (1-4094)
- Frame-Zuordnung anhand der VLAN-ID
- Geräte im selben VLAN → gleiche Broadcast-Domäne
## Einrichtung im Netzwerk
- Konfiguration auf Switches
- Zuordnung:
	- Ports → VLANs
	oder
	- per Tagging über Trunks
- Routing zwischen VLANS durch Router / L3-Switch

Notes:
- Jeder Switch-Port wird einem VLAN zugewiesen (Alles, was darüber ankommt, gehört zu dem VLAN)
## Portbasierte vs. Protokollbasierte VLANs

| Portbasiert                              | Protokollbasiert                          |
| ---------------------------------------- | ----------------------------------------- |
| Port ist festem VLAN zugeordnet          | VLAN-Zuordnung durch Protokolle (z.B. IP) |
| Einfach, übersichtlich & weit verbreitet | Flexibler, aber komplexer                 |
|                                          | weniger verbreitet                        |

## Auswirkungen auf Broadcast-Domänen
- Jedes VLAN bildet eigene Broadcast-Domäne
- Broadcasts bleiben innerhalb VLANs
- Weniger Broadcast-Verkehr
- Bessere Netzwerk-Performance & Stabilität
## Tagging (IEEE 802.1Q)
- VLAN-Zugehörigkeit im Frame gespeichert
- 802.1Q fügt VLAN-Tag hinzu
- Tag enthält VLAN-ID
- Ermöglicht VLAN-Zuordnung ohne Endgeräteport
## Trunk-Ports
- Trunk-Port verbindet Switches
- Transportieren mehrere VLANs gleichzeitig
- Frames sind:
	- getaggt (mehrere VLANs)
	- untagged → Native VLAN
- Voraussetzung für VLAN-übergreifende Netze
## Inter-VLAN-Routing
- VLANs sind logisch getrennt
- Kommunikation nur über Layer 3
- Per Router oder L3-Switch
- Routing entscheidet, welches VLAN erreicht wird
## Vor- und Nachteile

| Vorteile                          | Nachteile                                   |
| --------------------------------- | ------------------------------------------- |
| Bessere Sicherheit                | Höherer Konfigurationsaufwand               |
| Weniger Broadcasts                | Fehleranfälliger bei falscher Konfiguration |
| Flexible Netzwerkstruktur         | Limitierte VLAN-IDs                         |
| Logische Trennung von Abteilungen |                                             |
| Kostengünstiger                   |                                             |
## Fazit
- VLANs strukturieren Netzwerke logisch
- Trennung ohne zusätzlicher Hardware
- Standard in modernen Netzwerken
- Grundlage für Sicherheit & Skalierbarkeit
## Quellen
- https://en.wikipedia.org/wiki/VLAN
- https://www.geeksforgeeks.org/computer-networks/virtual-lan-vlan/
- https://en.wikipedia.org/wiki/IEEE_802.1Q