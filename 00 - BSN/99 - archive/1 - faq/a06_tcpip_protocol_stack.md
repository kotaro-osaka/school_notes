# FAQ A06 TCP/IP-Protocol-Stack
___
> IPv4/IPv6 // ARP // APIPA // SLAAC / Transport protocols //...
## 1.1
> Geben Sie die betreffenden CLI-Befehlszeilen an, um die o.a. Auflistungen (s.o. Bild 1 und Bild 2) zu erhalten!
1. `ipconfig /all`
2. `arp -a` (displays current arp cache as table)
## 1.3
> Herbert analysiert anhand der vorliegenden Netzwerkkonfiguration (s.o. Bild 1) dessen IPv6-Adresse. Geben Sie hierzu die nachfolgenden Werte bzw. Parameter (s.u.) an!
1. Länge der IPv6-Adresse in Bits: `128-bit`
2. Ungekürzte Darstellung der IPv6-Adresse in Hex Schreibweise: `fe80:0000:0000:0000:521a:c5ff:fef2:38b7`
3. Präfixlänge: `5`
4. Interface ID: `521a:c5ff:fef2:38b7`
5. Erstellung der Interface ID: SLAAC oder MAC-Adresse-basierte Generierung
	1. Splitting: `48-bit` MAC-Adresse in 2 `24-bit` Hälften teilen
	2. `FFFE`: `FFFE` zwischen beiden `24-bit`-Hälften einfügen (`=64-bit`)
	3. Siebtes Bit: 7. Bit der Interface ID bestimmen (`0`=public, `1`=private) 
## 1.4
> Nennen Sie in Bezug auf die hier vorliegende Netzwerkkonfiguration von Herberts Client-PC (s.o. Bild 1) die betreffenden Informationen bzw. Werte (Parameter), die er als DHCP-Client automatisch per DHCP erhalten bzw. zugewiesen bekommen hat!
- IPv4-Adresse
- Subnetzmaske
## 1.5
> Geben Sie an, wofür die Abkürzung "ARP" steht, und geben Sie die OSI-Layer ( Nr. und Name ) an, der dieses Protokoll am ehesten zuzuordnen ist!
- "Address Resolution Protocol"
- Network Layer 3
## 1.6
> Erläutern Sie kurz anhand von Bild 2 ( s.o. ), welche grundlegende Aufgabe das Protokoll "ARP" übernimmt und was im Listing von Bild 2 dargestellt wird!
- Löst Zuordnungen von IP-Adressen zu MAC-Adressen auf
- `arp -a` zeigt die Cache Tabelle des Localhosts (Geräte, mit denen neulich kommuniziert wurde)
- Informationen
	- Interface, wofür die ARP-Tabelle angezeigt wird
	- IP-Adresse des Interfaces
	- Hex-wert der ARP-Typcode repräsentiert 
	- IP-Adresse
	- MAC-Adresse
	- Typ (**Dynamische** Zuordnung durch Kommunikation // **Statischer** Eintrag)
## 1.7
> Geben Sie eine geeignete CLI-Befehlszeile an, um von Herberts Client-PC aus die Erreichbarkeit eines Rechnersystems zu prüfen, das sich im gleichen LAN wie Herberts PC befindet!
- `ping <Ziel-IP-Adresse>`
## 1.8
> Erklären Sie kurz, wofür die beiden Abkürzungen "APIPA" und "SLAAC" stehen und welche funktionale Bedeutung sich hinter diesen beiden IT-Fachbegriffen in Bezug auf die "IP-Autokonfiguration" verbirgt!
- APIPA: *Automatic Private IP Addressing*
	- Windows
	- Verwendung wenn DHCPLOOKUP keinen Server findet
	- Host generiert eigene IP-Adresse
	- IP-Adressbereich: `169.254.0.1-169.254.255.254`
	- Subnetzmaske: `255.255.0.0`
- SLAAC: *Stateless Address Autoconfiguration*
	- IPv6 Mechanismus
	- Wird verwendet um eigene IPv6-Adresse aus MAC und Router advertisements



## 4.
> Für Port-Nummern ist im Header des Transportprotokolls (TCP und UDP) eine Größe von 16 Bit (2 Byte) vorgesehen. Wie viele unterschiedliche Verbindungen könnte ein Host daher theoretisch gleichzeitig aufbauen? Geben Sie Ihr Ergebnis mit einer entsprechenden Rechnung an.
- Anzahl der möglichen Port-Nummern: $216=65.536216=65.536$
- Da sowohl die Quell- als auch die Zielportnummer für eine Verbindung verwendet werden, müssen wir die Anzahl der möglichen Verbindungen verdoppeln $65.536×2=131.07265.536×2=131.072$
$$131.072131.072$$
