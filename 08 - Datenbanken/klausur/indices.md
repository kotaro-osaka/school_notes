# Indices
___
- DB nutzen Indices zur Beschleunigung
- Ohne Index: Prüfung jeder Zeile nacheinander
- Mit Index: Direkter Sprung zur gesuchten Zeile
- Besteht aus Tabelle mit:
	- Indexwert
	- Pointer/RowID zum Datensatz
- Einsatzgebiete:
	- `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`
	- Eindeutige Werte (z.B. Primärschlüssel)

| Vorteile     | Nachteile                      |
| ------------ | ------------------------------ |
| Sehr schnell | Benötigt zusätzlichen Speicher |
|              | Wird bei Insert/               |
