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

1. Erstelle pro Tabelle einen Index bzw. zusammengesetzte Indizes
```mysql
CREATE INDEX idx_
```