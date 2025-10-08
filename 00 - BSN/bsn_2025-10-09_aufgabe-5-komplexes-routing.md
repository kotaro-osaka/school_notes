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
5. Welche Aufgabe hat der Eintrag “Default Ro”