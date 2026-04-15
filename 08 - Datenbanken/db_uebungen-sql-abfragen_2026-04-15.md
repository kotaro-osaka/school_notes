# Übungen - SQL Abfragen
___
**Gegeben:**
```
Schueler (SchuelerID, Name, Lieblingsfach, KlassenID)
Lehrer (LehrerID, Name, Fach)
Klasse (KlassenID, Bezeichnung, Raum)
Unterrichtet (LehrerID, SchuelerID)
```
## 1)
**Zeige alle Lehrer mit ihren Namen und die Klassen (Bezeichnung), die sie unterrichten mit denen, die keine Klasse haben.**
```mysql
SELECT Lehrer.Name, Klasse.Bezeichnung
FROM Lehrer
LEFT JOIN Unterrichtet ON Lehrer.LehrerID = Unterrichtet.LehrerID
LEFT JOIN Schueler ON Unterrichtet.SchuelerID = Schueler.SchuelerID
LEFT JOIN Klasse ON 
```