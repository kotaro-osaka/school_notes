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
- Authentifizierung
- Einfache Bedienung
- Konsistenz
- Erweiterbar
### Weitere Punkte
- Systemabgrenzung: Teil von AmNetPrime
- Use Cases
	- Favorit hinzufügen
	- Favoriten sortieren
	- Login
- Datenmodell
	- User (user_id, passwort)
	- Film (film_id, filmname)
	- Favoritenliste (liste_id, user_id, filmname)
- Randbedingungen
	- Funktion muss in erster Version enthalten sein
- Abnahmekriterien
	- Persistente Speicherung von Favoriten
	- Zugriff ohne Login nicht möglich