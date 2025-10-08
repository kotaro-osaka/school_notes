# Aufgabe 5 - Komplexes Routing
___
1. Warum benötigt ein Router in der Regel mindestens zwei Netzwerkadapter, um das Routing durchführen zu können?
	→ Da ein Router die Aufgabe hat Pakete von ein Netz in ein anderes zu leiten
2. Auf welcher Schicht des OSI-Modells wird das Routing durchgeführt?
	→ Dritte Schicht (Netzwerkschicht)
3. Beschreibe wesentliche Merkmale des statischen Routings
	1. Routen sind fest vorgeschrieben
	2. RIP Protokoll
	3. Protokoll bestimmt welche Route basierend auf Metrik Bedingungen verwendet wird
4. Wozu benötigt jeder Host eine Routingtabelle (`route print`)
	→ Wenn er Pakete an externe Netze versenden möchte, muss er Zieladresse, Standard Gateway, Subnetzmaske, Interface und Metrik kennen und interpretieren
5. Welche Aufgabe hat der Eintrag “Default Route”?
	→ Wird meist für Internetverbindung verwendet
	→ Ist die Adresse, die verwendet wird, wenn andere nicht erreichbar sind oder nicht zur gewünschten Zieladresse führen
6. Wie findet der Router den Weg zu einer Ziel-IP-Adresse (z.B. im Internet), wenn der Router nicht direkt mit dem zugehörigen Netzwerk verbunden ist?
	→ Er entpackt das Frame bis auf die Netzwerkebene und liest aus dem IP-Header des Pakets, von welchem Port an welche Gateway das