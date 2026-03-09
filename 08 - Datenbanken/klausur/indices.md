# Indices
___
## Beschreibung
*Indices sind Datenstrukturen, die schnellen Zugriff auf Datensätze ermöglichen.
Indices beschleunigen Abfragen, da Informationen statisch gechached werden, was bedeutet, dass das DBMS nicht die gesamte Tabelle durchsuchen muss.*

- Ohne Index: Prüfung jeder Zeile nacheinander
- Mit Index: Direkter Sprung zur gesuchten Zeile
- Besteht aus Tabelle mit:
	- Indexwert
	- Pointer/RowID zum Datensatz
- Einsatzgebiete:
	- `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`
	- Eindeutige Werte (z.B. Primärschlüssel)
## Vorteile & Nachteile

| Vorteile                                  | Nachteile                                 |
| ----------------------------------------- | ----------------------------------------- |
| Schnellere Abfragen                       | Erhöhter Speicherbedarf                   |
| Bessere Performance bei häufigen Abfragen | Verlangsamt Insert/Update/Delete          |
| Optimiert Joins und Sorts                 | Hohe Verwaltungskosten bei vielen Indizes |
## SQL
### Create
```mysql
CREATE INDEX idx_table_column
ON table(column);

-- Beispiel
CREATE INDEX idx_kunde_kundenname
ON kunde(kundenname);
```
### Drop
```mysql
DROP INDEX idx_table_column;

-- Beispiel
DROP INDEX idx_kunde_kundenname;
```