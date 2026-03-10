# Favoritenliste
___
## Funktionale & Nicht-Funktionale Anforderungen
### Funktionale Anforderungen
- Filme zu Favoriten hinzufügen
- Favoriten entfernen
- Reihenfolge der Favoriten festlegen (ASC / DESC)
- Mehrere Favoritenlisten anlegen
- Login mit UserID + Passwort
- Individuelle Favoriten pro Benutzer
- Zentrale SQL-Datenbank
### Nicht-funktionale Anforderungen
- **Sicherheit**: Authentifizierung
- **Performance**: Favoriten schnell laden, Datenbankzugriffe optimieren
- **Benutzerfreundlichkeit**: Einfache Bedienung, Klare Rückmeldung bei Aktionen
- **Zuverlässigkeit**: Keine Datenverluste, Konsistenz zwischen Favoriten und Filmen
- **Skalierbarkeit**: Muss für viele Benutzer gleichzeitig funktionieren
- **Wartbarkeit**: Erweiterbar für spätere Funktionen
### Weitere Punkte
- (Ausgangssituation & Zielsetzung)
- (Lebenszyklus des Gesamtsystems)
- ()
- **Systemabgrenzung**: Teil von AmNetPrime
- **Use Cases**
	- Favorit hinzufügen
	- Favoriten sortieren
	- Login
- **Datenmodell**
	- User (user_id, password)
	- Film (film_id, film_name)
	- Favoritenliste (liste_id, user_id, liste_name, film_name)
- **Schnittstellenübersicht**: Datenbank ←→ GUI
- **Randbedingungen**: Funktion muss in erster Version enthalten sein
- (Qualitätskriterien: Reaktionszeiten, Fehlertoleranz, Datenschutzanforderungen)
- **Abnahmekriterien**
	- Persistente Speicherung von Favoriten
	- Zugriff ohne Login nicht möglich
## Vorgehensmodell
### Trial and Error
- Einfaches Phasenmodell (Coding → Fehlersuche & -beseitigung 🔁)
- Ich als alleiniger Developer halte das Projekt für sehr übersichtlich (Würde dieses Modell nur bei Solo-Dev verwenden)
- Habe gute Vorstellungen von der Umsetzung
- Bin überzeugt, dass andere Modelle nur unnötig Zeit kosten würden
- Für eine erste Version ausreichend
- Später Kann man immer noch problemlos zu anderen Vorgehensmodellen migrieren
- Onboarding von neuen Devs ist trotzdem einfach, da dies nicht die Dokumentation ersetzt
## PSP
### 1) Projektmanagement
1.1 Projektplanung
1.2 Ressourcenplanung
1.3 Zeitplanung
1.4 Projektdokumentation
1.5 Abnahme Vorbereiten
### 2) Analysephase
2.1 Anforderungen analysieren
2.2 Funktionale Anforderungen definieren
2.3 Nicht-funktionale Anforderungen definieren
2.4 Use Cases erstellen
2.5 Pflichtenheft erstellen
### 3) Systementwurf
3.1 Architektur festlegen
3.2 Datenbankstruktur entwerfen
	3.2.1. Benutzer
	3.2.2 Filme
	3.3.3 Favoritenlisten
3.3 GUI entwerfen
	3.3.1 Auswahl Favoritenliste
	3.3.2. Hinzufügen & Entfernen Favoritenlisten
	3.3.3 Hinzufügen & Entfernen Favoriten
	3.3.4 Sortierfunktion
### 4) Implementierung
4.1 Datenbank implementieren
4.2 Funktion Favoritenverwaltung
	4.2.1 Favorit hinzufügen
	4.2.2 Favorit löschen
	4.2.3 Reihenfolge ändern
	4.2.4 Mehrere Listen verwalten
4.3 Benutzerverwaltung anbinden
4.4 GUI umsetzen
### 5) Testphase
5.1 Funktionen testen
5.2 Integration mit Datenbank testen
5.3 Sicherheitstest (Authentifizierung)
5.4 Fehlerbehebung
### 6) Einführung
6.1 Funktion in AmNetPrime integrieren
6.2 Dokumentation erstellen
6.3 Abnahme