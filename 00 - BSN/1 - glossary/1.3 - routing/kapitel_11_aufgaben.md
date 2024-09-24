# Kapitel 11 Aufgaben
___
## 1.
> Was ist die Kernaufgabe eines Routers?
- **Paketaustausch** zwischen 2 Netzwerken/Netzwerksegmenten
## 2.
> Was ist Statisches und Dynamisches Routing
### Statisches Routing
- Admin legt manuell fest, welche Routen ein Router verwendet werden soll
	→ Durch Konfiguration der Routingtabellen (des Routers)
### Vorteile | Nachteile
- Einfachere Implementierung
- Weniger Flexibel
- Nicht für große Netzwerke geeignet
### Dynamisches Routing
- Routingtabellen werden automaisch durch Protokolle aktualisiert (basierend auf Netzwerkveränderungen)
### Vorteile | Nachteile
- Bessere Skalierbarkeit & Anpassfähigkeit
- Mehr Overhead & komplexe Konfiguration
## 3.
> Aufbau einer Routingtabelle

![[routing_table.jpg]]
**Metrik**: Parameter des Routingalgorithmus’
## 4.
> Was ist Distance Vector Routing und Link State Routing

![[../../0 - res/routing_protocols.png|500]]
### Distance Vector Routing
> [[00 - BSN/1 - glossary/1.3 - routing/dvr|DVR]]
- Router tauschen periodisch Vektoren aus, um Routingtabellen zu aktualisieren
	→ Vektoren stellen Hop-Anzahl zu verschiedenen Zielen im Netzwerk dar
	→ [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/rip|RIP]]
### Link State Routing
> [[00 - BSN/1 - glossary/1.3 - routing/lsr|LSR]]
- Abstrakte Karte wird mit Statusinformationen der Router erstellt
- Router tauschen Statusinformationen über Zustände ihrer Links aus
	- **Link**: Verbindung zwischen 2 Routern
- Berechnet niedrigste Anzahl an Hops zu jedem Node im Netzwerk mit **Karte**
- ~~Vektoren~~, Informationen über Zustände der Links
- [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/ospf|OSPF]]
- [[00 - BSN/1 - glossary/1.3 - routing/1.3.0 - routing protocols/is-is|IS-IS]]
