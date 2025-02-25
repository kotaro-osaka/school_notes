# Internet Gefahren
___
## Arten
1. Phishing-Mails
	- Zahlungsaufforderungen
	- Ziel: An persönliche Daten des Empfängers gelangen
2. Verseuchte Websites & Apps
	- Herunterladen von Schadsoftware durch besuchen einer Website oder App-Download
	- Kann sich auf PC oder im Netzwerk ausbreiten
3. USB-Sticks
	- USB-Sticks mit Schadsoftware werden von Unwissenden an PC angeschlossen
4. Software-Schwachstellen
	- Sicherheitslücken in Software ausnutzen
5. Man in the Middle-Angriffe
	- Abfangen von Daten während der ungesicherten Übertragung/Kommunikation
6. DDoS-Attacken
	- "Distributed-Denial-of-Service" (verteilter DoS-Angriff)
	- Überlastung von IT-Infrastruktur
	- Bsp.: UDP-Flood
	- Angreifer können Botnet oder Zombie-Geräte (Ferngesteuerte infizierte Geräte) sein
7. Insider-Bedrohungen
	- Mitarbeiter oder Angestellte von IT-Dienstleistern nutzen Zugriffsmöglichkeiten aus
	- Daten löschen stehlen, löschen oder manipulieren
8. Vanity-URLs
	- Manipulation von Links für Phisching-Zwecke
9. reCaptcha-Abfragen
	- "Completely Automated Public Turing test to tell Computers and Humans Apart"
	- Phishing-Website durch Sicherheitsabfrage seriöser Unternehmen glaubwürdig wirken lassen
10. Rootkit
	
## Schutzmaßnahmen
- Advanced Persistent Threats
	-> Gegenstrategien:
	- Kombination aus Sicherheitsebenen (Firewalls, Virenfilter, Verschlüsselung, Antivirusprogramme, etc.)
	- Überwachung von Zugriffen durch IAM (Identity Access Management)
	- Mitarbeiter schulen und für Gefahren sensibilisieren
### WPA3 (WiFi Protected Access 3)
- SAE = "Simultaneous Authentication of Equals"
	- Basiert auf "Dragonfly-Handshake"-Protokoll
	- Ermöglicht sicheren Austausch von Schlüsseln Passwort-basierter Authentifizierungsmethoden
	- Ersetzt bisherige Methoden zur Aushandlung der Sitzungsschlüssel mit PSK (Pre-Shared Key)
	- Kommt auch in WLAN-Mesh-Implementierungen zum Einsatz
	- Variante des RFC 7664 spezifizierten "Dragonfly-Key-Exchange"-Protokolls
		- Basiert wiederum auf "Diffie-Hellmann"-Schlüsselaustausch
	- Wird in WLAN-Mesh-Netzwerken nach IEEE 802-11s während Discovery-Prozess der Peers verwendet
	- Verbessert Sicherheit des Schlüsselaustauschs im Handshake-Verfahren
#### Funktionsweise
- Nutzt übereinstimmende Passwörter, mit denen Clients Zugang zu WLAN erhalten
- Aus Passwörtern wird eindeutiger und bei jedem Client wird anderer (PMK) Pairwise Master Key abgeleitet
- Jeder Client erhält eigenen PMK trotz gleichen Passworts
- Mittels 4-Way-Handshake zwischen WLAN-Client und Authentifikationsserver Ableitung von PTK (Pairwise Transient Keys)
	- Eigentliche Verschlüsselung der Daten
