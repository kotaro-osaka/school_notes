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
CREATE INDEX idx_fahrgeschaeft_name ON Fahrgeschaeft(Name);

CREATE INDEX idx_mitfahrer_datum ON Mitfahrer (Datum);

CREATE INDEX idx_personal_nachname ON Personal (Nachname);

CREATE INDEX idx_unterkunft_adresse ON Unterkunft (Adresse);

CREATE INDEX idx_besucher_nachname ON Besucher (Nachname);
```

```mysql
CREATE INDEX idx_mitfahrer_fahrgeschäft_datum ON Mitfahrer (FahrgeschaeftBezeichnung, Datun);

CREATE INDEX idx_besucher_name ON Besucher (Nachname, Vorname);
```

1. Wieviele Besucher sind am *11.06.2025* mit dem Fahrgeschäft “*Rennmaus*” mitgefahren?
```mysql
SELECT f.Name, COUNT(*) AS 'num_besucher', m.Datum
FROM Mitfahrer m
JOIN Fahrgeschaeft f ON m.FahrgeschaeftBezeichnung = f.Bezeichnung
WHERE f.Name = 'Rennmaus'
	AND m.Datum = '11.06.2025';
```

2. Liste die Anzahl der Besucher pro Fahrgeschäft auf für den *07.08.2025*
```mysql
SELECT f.Name, COUNT(*) AS 'num_besucher', m.Datum
FROM Mitfahrer m
JOIN Fahrgeschaeft f ON m.FahrgeschaeftBezeichnung = f.Bezeichnung
WHERE m.Datum = '07.08.2025'
GROUP BY f.Name
ORDER BY num_besucher;
```

3. Liste alle Besucher auf, die ein ‘t’ im Nachnamen haben und das Fahrgeschäft “Eisachterbahn” besuchen.
```mysql
SELECT f.Name, b.Nachname, b.Vorname
FROM Fahrgeschaeft f
LEFT JOIN Mitfahrer m ON f.Bezeichnung = m.FahrgeschaeftBezeichnung
LEFT JOIN Besucher b ON m.BesucherID = b.ID
WHERE f.Name = 'Eisachterbahn'
    AND b.Nachname LIKE '%t%';
```