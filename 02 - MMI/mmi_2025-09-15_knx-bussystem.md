# Bussysteme
___
## Zukunft & Vergangenheit
- Fortschrittliche Technologien im Alltag: Kommunikation, Unterhaltung und Auto sind stark von modernen Technologien geprägt, die unseren Alltag vereinfachen und effizienter gestalten
- Veraltete Technologien im Gebäudebau: Im Gegensatz dazu hinken Gebäudetechnologien hinterher, wobei konventionelle Lösungen und mangelnde Automatisierung vorherrschen
- Energieverschwendung im Haushalt: Mangelnde Automatisierung und Steuerung führen zu Energieverschwendung, da beispielsweise die Heizung die Temperatur hält, auch wenn Fenster offen stehen
## Nachholbedarf in der Elektroinstallation
- Elektroinstallationen in bestehenden Gebäuden benötigen Nachrüstung, da Vernetzung und Flexibilität für zukünftige Anpassungen wichtig sind.
## Mehr Vernetzung
- Intelligentes Gebäude → Sensoren, Aktoren und deren Vernetzung
### Konventionelle Möglichkeiten
### Bustechnik
- Bussysteme ist überall in vielen arten sichtbar. 
- Bussysteme ist laut der pdf alle Sensoren, ein Kabel, sodass jeder sensor kommunizieren kann
- man kann alles Denkbare einbeziehen. 
- eine gute Lösung ist so etwas als Sternverkabelung auszuführen, d.h.: 1. alle Lichtschalter mit 5 drahtiger NYM-Leitung auf einer zentralen Verteilung zu verdrahten, 2. Die Leitung mit Schützen, Schaltrelais und einer SPS die logischen Beziehungen flexibel per Programm herzustellen. 
- jedoch ist es deutlich besser: 
	1. alle Sensoren und Aktoren im Gebäude über einer Datenleitung zu verbinden. Sodass jedes gerät verbunden miteinander kommunizieren kann.
## Warum KNX?
- Wird von vielen Herstellern unterstützt
- Alle starken Marked der Gebäudeinstallation treiben KNX voran
- Wurde gezielt für Anforderungen der Gebäudeinstallation entwickelt
- Installation & Programmierung/Parametrierung der Geräte erfolgt qualifiziert durch Systemintegratoren
- Etabliert
- Enormer Funktionsumfang
- Mehrere Tausend KNX zertifizierte Produktgruppen decken alle denkbaren Anwendungen ab
- Produkte werden durch dritte unabhängige Instanz auf Konformität geprüft
- Produkte sind herstellerübergreifend kompatibel (**Interworking**)
- Endkunden können auf Netz von Fachhandwerkern mit fundierten KNX Kenntnissen zurückgreifen
	- Deren Qualifikation wird durch KNX zertifizierte Schulungsstätten sichergestellt
- Software Tool **ETS** erlaubt *Planung*, *Projektierung* und *Inbetriebnahme* aller KNX zertifizierter Produkte unabhängig vom Hersteller
- Unterstützt alle Übertragungsmedien:
	- TP (Separates Zweidraht-Buskabel)
	- PL (Stromleitung)
	- RF (Funk)
	- IP/Ethernet/WLAN
- Weltweit standarisiert
	- CENELEC EN 50090 (Europa)
	- CEN 13321-1/2 (Europa)
	- ISO/IEC 13543-3 (International)
	- GB/T 20965 (China)
	- ANSI/ASHRAE 135 (USA)
- Mehr als 356 Mitglieder in 37 Ländern fertigen Produkte konform zum KNX Standard
	- Untereinander kompatibel
	- Spätere Änderungen/Erweiterungen der Installation sind problemlos möglich

## Rechnet sich eine Businstallation?
![[99 - misc/Screenshot 2025-09-15 at 12.05.28.png|500x500]]
> Studie “Energieeinsparpotenzial durch moderne Elektroinstallation”
 » Mit vernetzter Haus- und Gebäudesystemtechnik auf Basis von KNX sind Energieeinsparungen bis zu 50% möglich

### Argumente für Businstallation
- Einfacherer und kosteneffizientere Installation bei Anlagen mit umfangreichen Funktionswünschen  durch Kunden
- Geringere Komplexität bei Anlagen mit umfangreichen Funktionswünschen durch Kunden
- Fortlaufende Energieeinsparungen (Reduktion der Betriebskosten)
- Komfortgewinn Erleichterungen um Alter/Altersgerechtes Wohnen
- Zukunftssicherheit & Flexibilität der Installation
- Sicherheit
	- Anwesenheitsinstallation
	- Alarmierung bei Einbruchsversuch
	- Abtaualarm der Gefriertruhe
	- Paniktaster mit Meldung über Telefon
	- …
- Anwendung meistens im Zweckbau (Schulen, Veranstaltungszentren, Bürogebäude, Hotels, Praxen, Kanzleien & Produktionsstätten)

## Wieso heißt das System KNX?
KNX hieß voher "Europäischer Installationsbus (EIB)", nach einem Zusammenschluss mit der EIB-Association (EIBA), der Batibus Club International (BCI) und der European Home System Association (EHSA), wurde der Name KNX verwendet. KNX- und EIB-Geräte sind zueinander kompatibel, da die KNX Geräte mit der Technik des EIB-Systems kompatibel sind.
## Was ist das KNX System?
Das KNX System ist ein Bussystem für die Gebäudesteuerung. Alle Geräte benutzen das gleiche Übertragungsverfahren und die Daten tauschen über eine gemeinsame Busleitung aus. Der Zugriff auf die Busleitung muss eindeutig geregelt werden. Die meisten übertragenen Daten sind Adressinformationen und keine Nutzdaten. Adressinformationen: von wem kommen die Daten, an wen sind die gerichtet? Es ist kein zentrales Steuergerät notwendig, da die Intelligenz des Systems über alle Teilnehmer verteilt ist. Zentrale Geräte kann man jedoch für z.B. spezielle Aufgaben verwenden, sind aber optional. Vorteil der Dezentralität: beim Ausfall eines Gerätes funktionieren die übrigen Geräte nach wie vor. Beim KNX System werden neben den Systemgeräten auch zwischen Sensoren und Aktoren unterschieden. Sensoren: Geräte, die Ereignisse erkennen und die Informationen in Datenpakete versendet Aktoren: Geräte, die Datenpakete empfangen und die enthaltenen Befehle in Aktionen umwandelt Sensoren stellen die Befehlsgeber und Aktoren die Befehlsempfänger dar.
## Wie groß kann das System werden?
Die Größe des Bussystems kann auf dem Bedarf angepasst werden und sind beliebig erweiterbar. Das Kleinste System verbindet einen Sensor mit einen Aktor. Beim weiteren Ausbau fügt man so viele Geräte zu, die für die Steuerungsaufgaben notwending sind. Die Erweiterung einer Anlage muss einer vorgeschriebenen Topologie folgen.
## Welche Übertragungsmedien gibt es?
Das KNX System verwendet viele Übertragungsmedien. KNX Twisted Pair (KNX TP): Übertragung über verdrillte Zweidraht-Datenleitung (Busleitung) KNX Powerline (KNX PL): Übertragung über das 230 Volt-Netz KNX Radio Frequency (KNX RF): Übertragung über Funk KNX IP: Übertragung über Ethernet