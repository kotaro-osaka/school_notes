# Netzwerksegmentierung
___
## Aufgabe 1
Gegeben
- **Netzadresse**: `192.168.35.0`
- **Subnetzmaske**: `255.255.255.0`
Gebraucht
- 6 Subnetze
### a) Wie lautet die Subnetzmaske?
- `255.255.255.224`
- `/27`
### b) Wie viele Subnetze werden durch die Subnetzmaske erzeugt?
→ 8 werden erzeugt (6 ohne Broadcast & Router)
### c) Gebe die Netzadressen aller verfügbaren Subnetze in CIDR-Darstellung an.
1. `192.168.35.0/27`