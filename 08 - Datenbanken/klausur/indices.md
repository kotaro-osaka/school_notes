# Indices
___
## Beschreibung
*Indices sind Datenstrukturen, die schnellen Zugriff auf Datensätze ermöglichen.
Indices beschl*

- Ohne Index: Prüfung jeder Zeile nacheinander
- Mit Index: Direkter Sprung zur gesuchten Zeile
- Besteht aus Tabelle mit:
	- Indexwert
	- Pointer/RowID zum Datensatz
- Einsatzgebiete:
	- `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`
	- Eindeutige Werte (z.B. Primärschlüssel)
## Vorteile & Nachteile

| Vorteile     | Nachteile                                                     |
| ------------ | ------------------------------------------------------------- |
| Sehr schnell | Benötigt zusätzlichen Speicher                                |
|              | Wird bei Insert/Update/Delete neu aufgebaut (**verlangsamt**) |
|              | Viele Indices → Schlechte Write-Performance                   |
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