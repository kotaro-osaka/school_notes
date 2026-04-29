# Indizes
___
**Relationen:**
```
Fahrgeschäft (Bezeichnung(PK), Name, Kapazität, Altersbeschränkung, Geschwindigkeit)

Mitfahrer (FahrgeschäftBezeichnung, BesucherID, Datum, Uhrzeit)

Personal (Nr (PK), Nachname, Vorname, Adresse_,_ Einkommen)

Unterkunft (Bezeichnung (PK), Kapazität, Adresse_)

Besucher (ID (PK), Nachname, Vorname, Alter, Adresse, Unterkunft)
```

### 2 - Erstelle pro Tabelle einen Index bzw. zusammengesetzte Indizes
```mysql
CREATE INDEX idx_ ON ();
```

1. Wieviele Besucher sind am *11.06.2025* mit dem Fahrgeschäft “*Rennmaus*” mitgefahren?
```mysql
SELECT COUNT(*) AS 'num_besucher_rennmaus'
FROM Fahrgeschäft
LEFT JOIN Mitfahrer ON Fahrgeschäft.Bezeichnung ON Mitfahrer.FahrgeschäftBezeichnung
LEFT JOIN Besucher ON Mitfahrer.BesucherID = Besucher.ID
WHERE Fahrgeschäft.Name = 'Rennmaus'
GROUP BY Fahrgeschäft.Name;
```

2. Liste die Anzahl der Besucher pro Fahrgeschäft auf für den 