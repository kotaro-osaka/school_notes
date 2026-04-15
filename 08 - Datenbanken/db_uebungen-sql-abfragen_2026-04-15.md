# Übungen - SQL Abfragen
___
**Gegeben:**
```
Schueler (SchuelerID, Name, Lieblingsfach, KlassenID)
Lehrer (LehrerID, Name, Fach)
Klasse (KlassenID, Bezeichnung, Raum)
Unterrichtet (LehrerID, SchuelerID)
```

1) **Zeige alle Lehrer mit ihren Namen und die Klassen (Bezeichnung), die sie unterrichten mit denen, die keine Klasse haben.**
```mysql
SELECT Lehrer.Name, Klasse.Bezeichnung
FROM Lehrer
LEFT JOIN Unterrichtet ON Lehrer.LehrerID = Unterrichtet.LehrerID
LEFT JOIN Schueler ON Unterrichtet.SchuelerID = Schueler.SchuelerID
LEFT JOIN Klasse ON Schueler.KlassenID = Klasse.KlassenID;
```

2) **Zeige alle Schüler mit Namen mit ihren Klassen und dem Klassenraum.**
```mysql
SELECT Schueler.Name, Klasse.Bezeichnung, Klasse.Raum
FROM Schueler
LEFT JOIN Klasse ON Schueler.KlassenID = Klasse.KlassenID;
```

3) **Zeige alle Schüler, die keinen Raum haben.**
```mysql
SELECT Schueler.Name
FROM Schueler
LEFT JOIN Klasse ON Schueler.KlassenID = Klasse.KlassenID
WHERE Klasse.Raum IS NULL;
```

4) **Zeige alle Schüler (Name) und ihre Lehrer (Name) und dem Fach, das der Lehrer unterrichtet. Sortiere die Schüler dem Namen nach absteigend.**
```mysql
SELECT Schueler.Name, Lehrer.Name, Lehrer.Fach
FROM Schueler
LEFT JOIN Unterrichtet ON Schueler.SchuelerID = Unterrichtet.SchuelerID
LEFT JOIN Lehrer ON Unterrichtet.LehrerID = Lehrer.LehrerID
ORDER BY Schueler.Name DESC;
```