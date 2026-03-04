# Wiederholung: SQL Abfragen
___
## Aufgabe 1 - Der Notenskandal

```mysql
-- Alle Studierenden, die in mind. einer Lehrveranstaltung eine Note <1,5 bekommen haben

SELECT * FROM Studierender
WHERE Belegung.Note > 1.5
LEFT JOIN Belegung ON Studierender.MatrikelNr = Belegung.MatrikelNr;
```

```mysql
-- Überprüfe, ob diese Studierenden mehr Lehrveranstaltungen bestanden haben, als der Durchschnitt aller Studierenden

SELECT 
```