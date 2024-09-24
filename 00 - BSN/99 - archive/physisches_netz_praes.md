# Netzausdehnungen
- Man unterscheidet zwischen verschiedene Netzwerkdimensionen
	- Kriterien zur Unterscheidung von Netzwerken
	- Beschränkungen
		- Reichweite: Physische Entfernung, die ein Netzwerk abdeckt
		- Geographische Ausdehnung: Geographische Gebiete, die ein Netzwerk Verbindet
- Austausch zwischen LANs, WANs und GANs ist üblich
- Teilnehmer in einem LAN können auch Teil eines WANs oder GANs sein
---
- PAN: *Personal Area Network* - z.B. Bluetooth
	- Begrenzte Reichweite (~10m)
	- Erstreckt sich auf eine individuelle Person
	- <u>Verwendung</u>
		- Persönliche Geräte miteinander verbinden
		- Datenaustausch
	- Typische PAN-Geräte: Smartphones, Laptops, Bluetooth-Verbindungen
- LAN: *Local Area Network* - z.B. Ethernet, WLAN
	- Befindet sich in begrenztem geographischen Bereich (z.B. Gebäude, Campus) 
	- <u>Verwendung</u>
		- Kommunikation zwischen Geräten im begrenzten Bereich
		- Nutzung gemeinsamer Ressourcen (z.B. Internet-Zugang, Drucker, Speicher, Rechenleistung, Dienste, Anwendungen)
	- Typische Verbindungstechnologien: Ethernet, WLAN
- MAN: *Metropolitan Area Network* - z.B. Regionales Netz
	- Erstreckt sich über größere geographische Region (z.B. Stadt, Metropolregion)
	- Erleichtern Kommunikation und Datenaustausch zwischen Verschiedenen Standorten in städtischen Umgebung
	- <u>Verwendung</u>
		- Werden von Unternehmen, Bildungseinrichtungen, Regierungen verwendet
		- Vernetzung von Standorten innerhalb einer Stadt
	- Typische Verbindungstechnologien: Ethernet, Glasfaser, drahtlose Verbindungen
- WAN: *Wide Area Network* - z.B. Öffentliches Netz (DSL, Mobilfunk)
	- Erstreckt sich über große geographische Entfernungen (z.B. Länder, Kontinente)
	- <u>Verwendung</u>
		- Vernetzung von globalen Unternehmen
		- Bereitstellung von Internetdiensten
		- Dienste von anderen nutzen / Eigene Dienste anbieten (z.B. Datenverarbeitung, Informationsaustausch)
	- Typische Verbindungstechnologien: Öffentliche Telekommunikationsnetze (Internet), private Leistungen, Satellitenverbindungen
- GAN: *Global Area Network* - z.B. Internet
	- Weltweite Kommunikation und Datenaustausch
	- Verbindet verschiedene WANs und MANs
	- <u>Verwendung</u>
		- An weltweit verfügbaren Kommunikationsanwendung teilnehmen (z.B. Internet, Telefonie, Messaging, E-Mail)
---
![[Pasted image 20230922081023.png|300]]
___
In der Regel sind PANs und LANs **privat**.
MANs, WANs und GANs können je nach Verwendungszweck und Infrastruktur sowohl **privat**, als auch **öffentlich** sein. 
___
- Internet
	- Öffentlich, weltweites Netzwerk von Computern & Servern
	- Globale Kommunikation
- Intranet
- Extranet
# TP-Kategorisierung
- KAT-7 & KAT-8 werden am häufigsten genutzt

| Kategorie | Maximale Übertragungsrate                        | Anwendungsgebiet                                                                                                                                                                                                                                                                   | Vermeiden                                                                                              |
| --------- | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| CAT 1     | Bis zu 1 Mbps (1 MHz)                            | Analoge Sprache, Telefon- und Modemkabel (ISDN)                                                                                                                                                                                                                                    | Nicht für moderne Datennetze geeignet                                                                  |
| CAT 2     | 4 Mbps                                           | Vor allem bei IBM-Kabelsystemen für Token-Ring-Netzwerke eingesetzt                                                                                                                                                                                                                | Nicht für moderne Datennetze geeignet                                                                  |
| CAT 3     | 16 Mbps                                          | Sprache (meist analog), 10BASE-T Ethernet                                                                                                                                                                                                                                          | Nicht für Hochgeschwindigkeits-Internetverbindungen oder Gigabit-Ethernet geeignet                     |
| CAT 4     | 20 Mbps                                          | In 16 Mbps Token-Ring genutzt, ansonsten eher weniger verwendet, war nur kurz ein Standard und hat sich nie durchgesetzt                                                                                                                                                           | Bietet begrenzte Geschwindigkeiten und sollte nicht für moderne Netzwerkanforderungen verwendet werden |
| CAT 5     | 100 MHz                                          | 100 Mbps TPDDI, 155 Mbps ATM, Nicht mehr unterstützt und durch 5E ersetzt, 10/100BASE-T, Token Ring, Analoge Sprache                                                                                                                                                               | Kann für ältere Netzwerke verwendet werden, aber nicht für Gigabit-Ethernet                            |
| CAT 5e    | 100 MHz                                          | 100 Mbps TPDDI, 155 Mbps ATM, Gigabit Ethernet, Bietet besseres NeXT als CAT 5                                                                                                                                                                                                     | Nicht für Hochgeschwindigkeitsanwendungen wie 10 Gigabit-Ethernet geeignet                             |
| CAT 6     | Bis zu 250 MHz                                   | Minimale Verkabelung für Data Center in TIA-942, Ersetzt CAT 5E schnell                                                                                                                                                                                                            | Geeignet für Gigabit-Ethernet, aber nicht für lange Strecken                                           |
| CAT 6a    | Getestet bis zu 500 MHz                          | Unterstützung für 10 Gigabit Ethernet (10GBASE-T), Kann abgeschirmt sein (STP, ScTP, S/FTP) oder nicht (UTP), Standard wurde im Februar 2008 veröffentlicht, Minimalanforderung für Data Center im ISO-Data-Center-Standard                                                        | Geeignet für Hochgeschwindigkeitsanwendungen, aber teurer als Cat 6                                    |
| CAT 7     | 600 MHz, gepaart mit Siemon-Verbindungen 1,2 GHz | Video-Unterstützung, Teleradiologie, Behörden- und Produktions-Umgebungen, Komplett abgeschirmtes System (S/FTP), das keine RJ45-Verbindungen nutzt, Abwärts-kompatibel mit hybriden Kabelsystemen, Bis Februar 2008 der einzige Standard, der 10GBASE-T auf 100 Meter unterstützt | Geeignet für Hochgeschwindigkeitsanwendungen, aber teurer als Cat 6                                    | 
| CAT 7a    | 1000 MHz                                         | Vier einzeln abgeschirmte Adernpaare innerhalb eines gemeinsamen Schirms (S/FTP), Telefon und CATV, 100BASE-TX über dasselbe Kabel, 10GBASE-T Ethernet                                                                                                                             |                                                                                                        |
| CAT 8     | 1600 MHz-2000 MHz                                | Einführung 2015 geplant, Vier einzeln abgeschirmte symmetrische Adernpaare innerhalb eines gemeinsamen Schirms (S/FTP), Telefon und PoE, 40GBASE-T Ethernet                                                                                                                        |  Für moderne Hochgeschwindigkeitsnetzwerke                                                                                                      |

- wo nicht einbauen (kat-8 für Rechenzentren)
# Zugangs- / Zugriffsverfahren
- Layer (untere)
- Protokolle
- Ethernet
# Netzwerktopologien
- Sterntopologie (wird am häufigsten verwendet)
- Layer 2
- CSMA ~~Tokens~~
- Physische und 

### Quellen
https://www.elektronik-kompendium.de/sites/net/0503271.htm