# VLAN
___
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
## VLAN-Tagging und Trunk-Ports
- Verteiler-Switch hat keine Endgerät
- VLAN-Zugehörigkeit über 802.1Q-Tag
- Tag enthält VLAN-ID
- 
## Inter-VLAN-Routing

## Vor- und Nachteile

## Fazit

## Quellen