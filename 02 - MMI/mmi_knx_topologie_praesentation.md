# Topologie
___
**Nachfolgende Abkürzungen werden verwendet**:
- BK = Bereichskoppler
- LK = Linienkoppler
- TLN = Teilnehmer
- LV = Linienverstärker (*seit 01/2019 nicht mehr aktuell*)
- SV/Dr = Spannungsversorgung mit Drossel
- S = Helligkeitssensor
- RZ = Routing-Zähler
- TP = Twisted Pair
## Einleitung
___
### Unterschied vor/nach 2018
#### Vor 2018
- Maximal 64 TP-Geräte an einem Liniensegment
- Ein Segment kann sich durch Linienverstärker erweitert werden
- Es können maximal 3 Verstärker angebracht werden
- Somit 256 TP-Geräte möglich
#### Nach 2018
- Maximal 256 TP-Geräte an einem Liniensegment ohne Linienverstärker

**Wichtige Hinweise**
- Die Topologie vor 2018 soll unverändert bleiben
	- ≤64 Geräte pro Linie
- Linienverstärker besitzen dieselbe Hardware, wie Koppler
- Anzahl möglicher Geräte einer Linie ist auch abhängig vom Stromverbrauch
## Gesamtübersicht
___
![[99 - misc/Pasted image 20240902083157.png|750]]
*Maximal-Ausbau einer KNX-TP-Installation nach 2018*
> Linienverstärker nicht notwendig
> Linien-Verlängerungen nicht möglich

### Übergeordnete Linie
- Übergeordnete Anschluss (“Nordpol”) von Linien-/Bereichskopplern
- **Hauptlinie** für Linienkoppler
- **Ethernet-Seite** für IP-Router
### Untergeordnete Linie
- Untergeordneter Anschluss (“Südpol”) von Linien-/Bereichskopplern
- **Linie** für Linienkoppler
- **TP-Seite** für IP-Router
## Linie
___
![[99 - misc/Pasted image 20240902083932.png|750]]
- Max. 256 Geräte
- Jeder TLN kann mit anderen TLN über Telegramme kommunizieren
- Jede Linie (*bis 2018: jedes Liniensegment*) benötigt eine eigene passende Spannungsversorgung mit Drossel
- Eigentliche TLN-Anzahl pro Linie (*bis 2018: Liniensegment*) ist von Spannungsversorgung und Leistungsaufnahme einzelner Teilnehmer abhängig
- Verzweigung von Busleitungen ist an beliebiger Stelle möglich
- **Erlaubte Strukturen**: Stern, Linie, Baum (bzw. beliebige Kombination)
- **Unzulässige Strukturen**: Ring-Strukturen

> [!info]
> Baumstrukturen sparen immer Leitungsmaterial ein
## Bereich
___
![[99 - misc/Pasted image 20240902084915.png|750]]
- Linienaufbau mit bis zu 15 Linien über eine Hauptlinie und Linienkoppler (LK)
- Hauptlinie ≤TLN (abzüglich der LK) 
- **LK** zählen zur untergeordneten Linie
- LV nicht in Hauptlinie verwenden
- Jede Linie (*vor 2018: jedes Liniensegment*) benötigt eigene SV/Dr
- Kann **>4000** TLN umfassen
## Mehrere Bereiche (Netz)
___
![[99 - misc/Pasted image 20240909114503.png|750]]
- Erweiterung durch BK
- BK werden über Bereichslinie (*Backbone*) verbunden
- BK zählen zu untergeordneten (Haupt-)Linien
- Keine LV in Bereichslinie
- Bereichslinie benötigt SV/Dr
- ≤256 TLN (abzüglich der BK)
- Kann **>61.000** TLN umfassen
## Physikalische Adresse
___
![[99 - misc/Pasted image 20240909115319.png|750]]
> *nach 2018*

- Physikalische/Individuelle Adresse dient zur eindeutigen Identifikation
- Beschreibt Anordnung innerhalb der Topologie

| Adressteil | Bereich |                 Beschreibung                 |
| :--------: | :-----: | :------------------------------------------: |
|     **B=**     |  1…15   |             Bereichsnummern 1…15             |
|     **B=**     |    0    |      Bereich für TLN auf Bereichslinie       |
|            |         |                                              |
|     **L=**     |  1…15   |      Liniennummer 1…15 im Bereich (*B*)      |
|     **L=**     |    0    | Liniennummer für Hauptlinie im Bereich (*B*) |
|            |         |                                              |
|     **T=**     |  1…255  |    TLN-Nummer für Geräte der Linie (*L*)     |
|     **T=**     |    0    |    TLN-Nummer des LK der jeweiligen Linie    |
- **Anfangszustand** eines entladenen TLN: **15.15.255**
- **Zustand/Adresse**, wenn über ETS entladen (zurückgesetzt): **15.15.255**
## Koppler - Schleusefunktion
___
![[99 - misc/Pasted image 20240909122430.png|750]]
- **Übergeordnete Funktionen**: Schleusefunktion innerhalb einer Linie
- **Physikalische Adressen**: Sicherstellung der korrekten Zuordnung
- **Telegrammweiterleitung**: Nur bei Übereinstimmungen bestimmter Kriterien
- **Filtertabelle**: Verwaltung der Gruppenadressen, die Telegramme erhalten
- **Telekommunikation**: Begrenzung/Erweiterung, je nach Einstellungen
- **Unabhängiger Betrieb**: Gerät arbeitet unabhängig von Steuerbefehlen eingehender Telegramme
## Koppler - Blockdiagramm
___
![[99 - misc/Pasted image 20240915204259.png|750]]
> Übergeordnete Linie: **Freileitung**
> Untergeordnete Linie: **Erdkabel**

- **Untergeregelte Linienkoppler**: Entkopplung von Hochfrequenzsignalen auf Freileitungen auf Erdkabel
- **Funktion**: Vermeidung von Interfrequenzen & Erhaltung von Signalqualität durch Linienkoppler (Trennung von Signalen zwischen verschiedenen Leistungstypen)
- **Anwendung**: Sicherstellung, dass Hochfrequenzsignale auf Freileitungen nicht Signale auf Erdkabeln stören
	→ Nützlich in komplexen Netzwerken mit verschiedenen Leistungstypen
## Koppler - Einsatzvarianten
___
![[99 - misc/Pasted image 20240915205143.png|750]]
- **BK**, **LK**, **LV** sind identische Geräte.
	→ Aufgabe ergibt sich durch topologischen Einbauort
### Verwendung
1. **BK** → Verbindung **Bereichslinie - Hauptlinie**
2. **LK** → Verbindung **Hauptlinie - untergeordnete Linie**
3. **LV** → (vor 2019:) Linienerweiterung um Liniensegment mit ≤64 weiteren TLN + 1000 m Leitung

- BK & LK leiten ausschließlich **Linien-übergreifende Telegramme** weiter
- Physikalische Adresse macht Koppler zu **BK**/**LK**/**LV**
- LK **filtert Datenkommunikation** zwischen Haupt- & Sekundärlinie
## KNX IP im Vergleich zu KNX TP
___
### IP
- **Hohe Kosten** für Verkabelung (jedes Endgerät benötigt eigene Netzwerkleitung)
- **Aufwendige Vernetzung** von KNX Hutschienenmodulen im Schaltschrank (viele Switches nötig, nicht energieeffizient)
- Bestehender Netzwerkanschluss am Gerät → KNX Gerät ohne zusätzliche Hardwarekosten (erfordert Systemsoftware)
### Zukunft
- **Ethernet** als leistungsfähiger Backbone & Anschluss für komplexe KNX IP Geräte
- **TP**, **PL**, **RF** bleiben wichtig für Anbindung verteilter Sensoren/Aktoren
## Datendurchsatz im Vergleich
___
### Einheitliches Bussystem
- Unterschiedliche Übertragungsmedien (TP, IP, PL, RF)
- Inbetriebnahme mit einer einzigen Software (ETS)
- Kommunikation unabhängig von Ankopplung (Systemweite Gruppenadressen, Herstellerkompabilität)
### Datendurchsatz
#### KNX TP
- Normale Telegrammübertragung: Ca. 20ms
- Programmierung: Ca. 40ms
- ≤50 Telegramme/s
#### KNX PL
- Niedrige Baudrate
- Längerer Telegrammaufbau
- Anderes Zugriffsverfahren
- ≤6 Telegramme/s
#### Erweiterbarkeit
- KNX Anlagen können auf **Teilanlagen unterschiedlicher Übertragungsmedien** bestehen
- Reibungslose Telegrammübertragung erfordert eine bestimmte Topologie