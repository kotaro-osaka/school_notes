# Aufgabe 5 - Komplexes Routing
___
[Aufgabenblatt](00%20-%20BSN/bsn_2025-10-09_Aufgabe4_NetzwerksegmentierungPackettracer.pdf)

#### 1. Warum benötigt ein Router in der Regel mindestens zwei Netzwerkadapter, um das Routing durchführen zu können?
> Da ein Router die Aufgabe hat, Frames von ein Netz in ein anderes zu leiten
#### 2. Auf welcher Schicht des OSI-Modells wird das Routing durchgeführt?
> Dritte Schicht (Netzwerkschicht)
#### 3. Beschreibe wesentliche Merkmale des statischen Routings
> 1. Routen sind fest vorgeschrieben
> 2. RIP Protokoll
> 3. Protokoll bestimmt welche Route basierend auf Metrik Bedingungen verwendet wird
#### 4. Wozu benötigt jeder Host eine Routingtabelle (`route print`)
> Wenn er Frames an externe Netze versenden möchte, muss er Zieladresse, Standard Gateway, Subnetzmaske, Interface und Metrik kennen und interpretieren
#### 5. Welche Aufgabe hat der Eintrag “Default Route”?
> → Wird meist für Internetverbindung verwendet
> → Ist die Adresse, die verwendet wird, wenn andere nicht erreichbar sind oder nicht zur gewünschten Zieladresse führen
#### 6. Wie findet der Router den Weg zu einer Ziel-IP-Adresse (z.B. im Internet), wenn der Router nicht direkt mit dem zugehörigen Netzwerk verbunden ist?
> Er entpackt das Frame bis auf die Netzwerkebene und liest aus dem IP-Header des Frames, die Zieladresse, sucht nach dessen Netzwerkadresse in der Routingtabelle, worin steht, von welchem Interface an welche Gateway das Frame versendet werden muss, um dahin zu gelangen
#### 7. Ein Router 1 hat zwei Netzkarten eingebaut, welche folgendermaßen konfiguriert sind:[Netzwerk](00%20-%20BSN/bsn_2025-10-09_Aufgabe4_NetzwerksegmentierungPackettracer.pdf#page=2&selection=31,0,31,2)
##### 1. Welche IP-Adresse muss in diesem Rechner als Standardgateway eingetragen werden?
> `192.168.33.1/24`
##### 2. Welche Informationen werden vom Router 1 benötigt, damit dieser das Datenpaket an den Empfänger weiterleiten kann?
> 1. Zielnetzwerk
> 2. Subnetzmaske
> 3. Interface
> 4. Gateway
#### 3. Was muss mit der privaten IP-Adresse des Absenders passieren, damit www.ostvest.de ein Antwortpaket zum Rechner 192.168.33.10/24 zurücksenden kann?
> Sie muss mithilfe der NAT-Tabelle in Router 2 in die zugehörige öffentliche Adresse verwandelt übersetzt werden.