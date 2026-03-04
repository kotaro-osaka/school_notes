# Wiederholung: SQL Abfragen
___
## Aufgabe 1 - Der Notenskandal

1.
```mysql
-- Alle Studierenden, die in mind. einer Lehrveranstaltung eine Note <1,5 bekommen haben

SELECT * FROM Studierender
WHERE Belegung.Note > 1.5
LEFT JOIN Belegung ON Studierender.MatrikelNr = Belegung.MatrikelNr;
```

2. + 3.
```mysql
-- Überprüfe, ob diese Studierenden mehr Lehrveranstaltungen bestanden haben, als der Durchschnitt aller Studierenden

SELECT * FROM Studierender
WHERE Belegung.Note > 1.5 &&
	Belegung.Status = 'Bestanden'
LEFT JOIN Belegung ON Studierender.MatrikelNr = Belegung.MatrikelNr;
```

## Aufgabe 2 - Doppeltes Identitätsproblem

1.
```mysql
-- Studierende, die gleichen Namen und E-Mail-Adresse haben

SELECT * FROM Studierender
WHERE Studierender.Name  &&
	Studierender.Email
```