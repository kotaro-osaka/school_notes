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
