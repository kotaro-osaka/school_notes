# Übungsaufgaben: SQL-Abfragen
___
**Relationen:**
```
Zoo(ZooID (PK), Name, Ort)

Gehege(GehegeID (PK), Name, Typ, ZooID (FK))

Tier(TierID (PK), Name, ArtID (FK), Geburtsdatum, GehegeID (FK))

Art(ArtID (PK), Bezeichnung, Herkunft, Schutzstatus)

Pfleger(PflegerID (PK), Name, Telefonnummer, ZooID (FK))

Pflege(PflegeID (PK), PflegerID (FK), TierID (FK), ZuständigSeit)

Futter(FutterID (PK), Bezeichnung, Typ)

Fütterung(FütterungID (PK), TierID (FK), FutterID (FK), Uhrzeit, Menge)
```

1. Zeige alle Tiere mit ihrer jeweiligen Art und dem Gehege, in dem sie leben.
```mysql
SELECT Tier.Name, Art.Bezeichnung, Gehege.Name
FROM Tier
LEFT JOIN Art ON Tier.ArtID = Art.ArtID
LEFT JOIN Gehege ON Tier.GehegeID = Gehege.GehegeID;
```

2. Zeige alle Pfleger und die Tiere, für die sie zuständig sind. Berücksichtige auch Pfleger ohne zugewiesene Tiere.
```mysql
SELECT Pfleger.Name, Tier.Name
FROM Pfleger
LEFT JOIN Pflege ON Pfleger.PflegerID = Pflege.PflegerID
LEFT JOIN Tier ON Pflege.TierID = Tier.TierID;
```

3. Zeige alle Tiere mit ihrem Geburtsdatum, sortiert nach dem Alter (älteste zuerst).
```mysql
SELECT Name, Geburtsdatum
FROM Tier
ORDER BY Geburtsdatum DESC;
```

4. Zeige, wie viele Tiere sich in jedem Gehege befinden.
```mysql
SELECT Gehege.Name, COUNT(*) AS 'Anzahl Tiere'
FROM Gehege
LEFT JOIN Tier ON Gehege.GehegeID = Tier.GehegeID
GROUP BY Gehege.GehegeID, Gehege.Name;
```

5. Welche Gehege haben mehr als 2 Tiere?
```mysql
SELECT Gehege.Name, COUNT(Tier.TierID)
FROM Gehege
JOIN Tier ON Gehege.GehegeID = Tier.GehegeID
GROUP BY Gehege.GehegeID, Gehege.Name
HAVING COUNT(Tier.TierID) > 2;
```

6. Welche Pfleger betreuen mehr als ein Tier und wie viele Tiere betreuen sie jeweils? Sortiere das Ergebnis nach der Anzahl der betreuten Tiere.
```mysql
SELECT Pfleger.Name, COUNT(Pflege.TierID)
FROM Pfleger
JOIN Pflege ON Pfleger.PflegerID = Pflege.PflegerID
GROUP BY Pfleger.PflegerID, Pfleger.Name
HAVING COUNT(Pflege.TierID) > 1
ORDER BY COUNT(Pflege.TierID) DESC;
```
