# Einführung Datenschutz vs. Datensicherheit
___
## Aufgabe 1
Nennen Sie schlagwortartig typische Praxisbeispiele für "IT-Security-Teilgebiete"!
- **Netzwerksicherheit**: Firewalls, Intrusion Detection/Prevention-Systeme (IDS/IPS)
- **Anwendungssicherheit**: Secure Coding, Penetrationstests
- **Datensicherheit**: Verschlüsselung, Backup-Strategien
- **Endgerätesicherheit**: Antivirus-Software, Mobile Device Management (MDM)
- **Identitäts- und Zugriffsmanagement**: Multi-Faktor-Authentifizierung (MFA), Single Sign-On (SSO)
- **Cloud-Sicherheit**: Zugriffskontrollen, Cloud Security Posture Management (CSPM)
- **Physische Sicherheit**: Zutrittskontrollen, Überwachungssysteme
- **Sicherheitsrichtlinien**: Schulungen, Incident-Response-Pläne
- **Schwachstellenmanagement**: Vulnerability Scans, Patch-Management
- **Betriebssystemsicherheit**: Hardening, regelmäßige Updates
## Aufgabe 2
Erklären Sie, worin sich die beiden IT-Fachbegriffe "**Datensicherheit**" und "**Datenschutz**" im Kern unterscheiden!

> *Datensicherheit*: Schutz der Daten vor Verlust und Manipulation
> 
> *Datenschutz*: Schutz von Personen vor der missbräuchlichen Verwendung von personenbezogen Daten; gesetzlich geregelt

## Aufgabe 4
### 4.1
Was bedeuten jeweils die IT-Fachbegriffe a) "_Vertraulichkeit_" von Daten, b) "_Integrität_" von Daten und c) "_Verfügbarkeit_" von Daten?
- Vertraulichkeit
	- Schutz vor unbefugtem Zugriff
- Integrität
	- Sicherstellung, dass Daten vollständig und unverändert bleiben, es sei denn, autorisierte Änderungen werden vorgenommen
- Verfügbarkeit
	- Daten und Systeme jederzeit zugänglich, wenn sie benötigt werden
### 4.2
Diskutieren und entscheiden Sie: Betreffen diese drei oben stehenden IT-Fachwörter (s.o.) eher den Datenschutz oder die Datensicherheit?
- Vertraulichkeit
	- Schutz vor unbefugtem Zugriff auf Hardware (Datensicherheit)
	- “ ” auf Daten (Datenschutz)
- Integrität
	- Schutz vor manipulation (Datensicherheit)
	- Schutz vor unbefugter Veränderung (Datensicherheit)
- Verfügbarkeit
	- Daten sind zugänglich, wenn sie benötigt werden (Datensicherheit)
	- Personenbezogene Daten sind zugänglich, wenn sie für rechtliche Zwecke benötigt werden (Datenschutz)
### 4.3
Benennen Sie typische Praxisbeispiele für gewollte "_Redundanzen_" innerhalb einer komplexen IT-Infrastruktur ( großes Netzwerk mit vielen Subnetzen EITS, Protokollen, umfangreicher HW, SW, Anwendungen etc. ) eines Unternehmens!

**Hardware**
- Redundante Server (Cluster Instanzen)
- RAID (verschiedene RAID-Level, je nach Gebrauch)
	- RAID 0: Striping (Verteilung auf mehrere Festplatten)
	- RAID 1: Mirroring (Identische Speicherung auf zwei Festplatten)
	- RAID 5: Datenverteilung mit Paritätinforationen
	- RAID 6: RAID 5 mit doppelter Parität (Daten zur Fehlererkennung und -korrektur)
	- RAID 10 (1+0): Gespiegelte gestripte Daten
	- RAID 50/RAID 60: RAID 5/6 + 0
- Backup-Stromversorgung (USV, Generatoren)

**Netzwerk**
- Mehrere Internet Service Provider (ISP)
- Redundante Switches und Router
- Mehrfach ausgelegte Netzwerkleitungen

**Software-Redundanz**
- Failover-Datenbanken
- Load Balancer für verteilte Anwendungen (auf mehrere Computer/Server verteilt)
- Redundante VMs

**Daten-Redundanz**
- Offsite-Backups
- Replikation von Datenbanken (Master-Slave-Setup)
- Cloud-Speicher-Dienste als zusätzliche Datenablage

**Protokoll- und Service-Redundanz**
- Mehrere DHCP-Server
- Redundante DNS-Server
- Verwendung von HSRP (Zweiter Router steht als Standby bereit), VRRP (Ein Master-Router, mehrere Backup-Router), GLBP (Mehrere Router teilen sich Aufgaben (Load Balancing, Ausfallsicherheit, Performance)) für Ausfallsicherheit

**Standort-Redundanz**
- Georedundante Rechenzentren
- Notfallarbeitsplätze an anderen Standorten
- Disaster Recovery Sites (Georedundante Standorte, von wo aus Hauptstandorte wiederhergestellt werden können)

**Sicherheit-Redundanz**
- Mehrfache Firewalls und Intrusion Detection Systeme (IDS)
- Backup für Authentifizierungsserver (z.B. Active Directory)
- Alternative VPN-Gateways für Remote-Zugriff
### 4.4
Finden Sie eine passende Übersetzung und Erklärung für die folgenden IT-Fachwörter: "_Failover_", "_Reliability_", "_Availability_" und "_Performance_"!

**Failover**: Ausfallsicherheit
> Automatischer Wechsel von fehlerhaften System/Dienst auf funktionierendes Backup-System

**Reliability**: Zuverlässigkeit
> Fähigkeit eines Systems/Komponente über längeren Zeitraum ohne Fehler/Ausfälle korrekt zu arbeiten

**Availability**: Verfügbarkeit
> Fähigkeit eines Systems/Dienstes, zu jeder gewünschten Zeit nutzbar zu sein

**Performance**: Leistung
> Fähigkeit eines Systems, Aufgaben schnell & effizient auszuführen

