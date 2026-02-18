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
1. Projektplanung
2. Ressourcenplanung
3. Zeitplanung
4. Projektdokumentation
5. Abnahme Vorbereiten
### 2) Analysephase
1. Anforderungen analysieren
2. Funktionale Anforderungen definieren
3. Nicht-funktionale Anforderungen definieren
4. Use Cases erstellen
5. Pflichtenheft erstellen
### 3) Systementwurf
1. Architektur festlegen
2. Datenbankstruktur entwerfen
	1. Benutzer
	2. Filme
	3. Favoritenlisten
3. GUI entwerfen
	1. Auswahl Favoritenliste
	2. Hinzufügen & Entfernen Favoritenlisten
	3. Hinzufügen & Entfernen Favoriten
	4. 