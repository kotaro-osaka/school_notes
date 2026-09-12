# Syntax
___
**DISTINCT** - Removes all duplicate rows (applied to all columns listed in `SELECT`)
```SQL
SELECT DISTINCT column, another_column, ...
FROM mytable
WHERE condition(s);
```

**ORDER BY** - Sort by given column (ASC default)
```SQL
SELECT column, another_column, ...
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```

**LIMIT|OFFSET** - Limit number of rows | Specify where to begin (optional)
```SQL
SELECT column, another_column, …
FROM mytable
WHERE _condition(s)
ORDER BY column ASC/DESC 
LIMIT num_limit OFFSET num_offset;
```

**INNER JOIN** - Only shows symmetric data
```SQL
SELECT column, another_table_colmn, ...
FROM mytable
INNER JOIN another_table
	ON mytable.id = another_table.id
WHERE condition(s)
```

**LEFT/RIGHT JOIN** - Keeps all data from table **A**(*LEFT*)/**B**(*RIGHT*) regardless of whether match found 
**FULL JOIN** - Keeps all data from both tables
(non-matching entries shown as null)

```SQL
# Specific column (relevance: column)
table.column

# Column in context of table (relevance: table + column)
table(column)
```

```SQL
CREATE TABLE IF NOT EXISTS table_name(
	id INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
	name VARCHAR(255) NOT NULL,
	age INT DEFAULT 18,
	email VARCHAR(255) UNIQUE, # Index creation
	registered_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
	country_id INT
	fk_example INT NOT NULL
	FOREIGN KEY (fk_example) REFERENCES other_table(fk_example)
		ON DELETE CASCADE
		ON UPDATE CASCADE,
	...
);
```

**ALTER TABLE**
```SQL
# Add Column
ADD column_name datatype

# Drop Column
DROP COLUMN column_name

# Modify Datatype
MODIFY COLUMN column_name datatype

# Modify Entries
SET value = new_value
WHERE condition(s)
```

**Constraints**
- NOT NULL - Ensures that a column cannot have a NULL value
- UNIQUE - Ensures that all values in a column are different
- PRIMARY KEY - A combination of a `NOT NULL` and `UNIQUE`. Uniquely identifies each row in a table
- FOREIGN KEY - Prevents actions that would destroy links between tables
- CHECK - Ensures that the values in a column satisfies a specific condition
- DEFAULT - Sets a default value for a column if no value is specified
- CREATE INDEX - Used to create and retrieve data from the database very quickly
# Normalisierung
___
**Ziel**: Anomalien beseitigen und Redundanzen minimieren

**1. Normalform**
Eine relationale Datenbank befindet sich in der ersten Normalform, wenn **alle Attribute atomar** sind. (d.h. spalte enthält einen wert pro Zeile)

**2. Normalform**
Eine relationale Datenbank befindet sich in der zweiten Normalform, wenn die **erste Normalform** erfüllt ist und **alle Nicht-Schlüsselattribute vollständig vom Primärschlüssel abhängig**

**3. Normalform**
Eine relationale Datenbank befindet sich in der zweiten Normalform, wenn die **zweite Normalform** erfüllt ist und kein Nicht-Schlüsselattribut von anderen Nicht-Schlüsselattributen abhängig ist. (*keine transitive Abhängigkeiten*)
> *transitiv*: Indirekte Beziehung
> **Beziehungen zwischen Nicht-Primärschlüsseln und Primärschlüsseln müssen direkt sein**

| Pro                                                                                                                           | Contra                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Minimiert Doppelungen von Datensätzen pro Tabelle                                                                             | Etwas komplexere Abfragen<br>(*Have to be able to find data from different parts of the database*) |
| Ermöglicht Daten unabhängig von einander zu wachsen<br>(*i.e. Types of car engines can grow independent of each type of car*) | Performance Probleme bei vielen großen Tabellen                                                    |
# Keys
___
**Foreign Key**
> Tabellen, die Informationen zu einer einzelnen Entität gemeinsam nutzen, müssen über einen Primärschlüssel verfügen, der diese Entität in der gesamten Datenbank eindeutig identifiziert.

**Foreign Key**
```SQL
FOREIGN KEY (id) REFERENCES other_table(id)
	ON DELETE CASCADE
	ON UPDATE CASCADE
```
## Indizes
___
**Erläuterung**
- **Datenstruktur** (Schlüssel, Pointer, Datenstrukturen (B-Tree/Hash-Table), Indexseiten, Metadaten)
- Falls richtig angewendet:
	- Abfragegeschwindigkeit von z.B. `SELECT`-Abfragen, `WHERE`-Klauseln minimieren
	- Indizierung eines oder mehrerer Attribute einer Tabelle
		- Auswahl des passenden Indizes beachten (z.B. Unique-Index, um Einzigartigkeit zu versichern)
		- Umsetzung durch SQL-Befehl
			- Bei Ausführung des Befehls werden zu indizierende Spalten in ihrer jetzigen Form auf der Festplatte gespeichert
			- Indizes werden (falls nicht zu groß) im RAM gespeichert, um Zugriffsgeschwindigkeit zu verringern
- Zusammengefasst: Wie Inhaltsverzeichnis eines Buchs/strukturierten Dokuments
	- Buch/Dokument: Datenbank
	- Inhaltsverzeichnis: Indizes
	- Kapitel: Attribute
	- Inhalt der Kapitel: Werte

### Arten
**Unique Index**
- Anwendung auf Attribute (oder Kombination von Attributen), die einzigartige und nicht-verändernde Werte besitzen
```SQL
CREATE UNIQUE INDEX idx_unique_column ON table_name(column_name);
```

**Clustered Index**
- Anwendung auf mehrere Attribute, die zu einem **gemeinsamen Index** indiziert werden sollen
- Nützlich, wenn mehrere Attribute häufig gemeinsam in Abfragen vorkommen
```SQL
# Automatically created on the primary key
```

**Full-Text Index**
- Optimieren Abfragegeschwindigkeit von Datensätzen, die viel Text als Werte beinhalten (z.B. Blogs, Artikel)
```SQL
CREATE FULLTEXT INDEX idx_fulltext_column ON table_name(column_name);
```

**B-Tree Index**
- Default Index-Typ
- Erstellt Referenzen auf Daten
	- Algorithmus unterteilt Daten schichtweise in jeweils zwei Abzweigungen
- **Vorteil**: Bereits nach erstem Durchlauf einer Abfrage kann die Hälfte der Daten ausgeschlossen werden
	- Prozess wiederholt sich, bis gewünschte Daten lokalisiert werden
```SQL
CREATE INDEX idx_btree_column ON table_name(column_name);
```

**Hash Index**
- Verwendung bei genauen Vergleichen (`=`)
- Ungeeignet für `<`, `>`, `BETWEEN` (Ordnung wird nicht beibehalten)
- Benötigt weniger Speicherplatz als andere Indizes, da Schlüssel nicht geordnet gespeichert werden
```SQL
CREATE INDEX idx_hash_column ON table_name(column_name) USING HASH;
```

## 3 Ebenen Modell
___
- Ermöglicht logische und physische Datenunabhängigkeit, sodass Änderungen auf einer Ebene andere minimal beeinflussen
- **Bsp**:
	- Änderung der Speicherstruktur (interne Ebene) sollte nicht die logische Datenstruktur (konzeptionelle Ebene) beeinträchtigen
	- Änderungen der Benutzersicht (externe Ebene) sollte keine Änderungen am konzeptionellen Schema erfordern
- Verwaltung erfolgt durch **Datenbankadmin**

**Externe Ebene**
- Benutzerdefinierte Wiedergabe von Daten je nach Gebrauchform (GUI für Ergebnisse von Nutzerabfragen/API für Abfragen von externe Anwendungen)
- Zeigen **abgefragte** Inhalte, die für den jeweiligen Gebrauch relevant sind (Teile von Objekten können abgefragt werden)
- DQL (Data Query Language) wird verwendet, um Daten zu lesen und zu manipulieren

**Konzeptionelle Ebene**
- Festlegung von Konzeptionellem Schema (Struktur der Datenbank(-logik))
- Verwaltung von Änderungsvorschriften
- DDL (Data Definition Language) wird verwendet, um Schema zu erstellen

**Interne Ebene**
- Organisation von Daten auf Speichermedien
- Verwaltung von Zugriffsmöglichkeiten auf Daten

**Transformationsregeln**
- Zuordnungsregeln (Mappings), die festlegen, wie Daten zwischen Ebenen transformiert werden

## Referenzielle Integrität
___
- Wird bei Erstellung von Datenbankstruktur sichergestellt
- Constraints stellen sicher, dass **Integritätsregeln** eingehalten werden
	- Beziehungen zwischen Tabellen sind logisch und konsistent
	- Verweise zeigen nicht auf ungültige Datensätze
- Automatische Maßnahmen bei Datenänderungen
	- `ON DELETE CASCADE`: Alle referenzierten Einträge werden ebenfalls gelöscht
	- `ON UPDATE CASCADE`: Aktualisierung von Primärschlüssel löst automatische Anpassung von entsprechenden Fremdschlüsseln aus

## Constraints
___
- `ON DELETE`
- `ON UPDATE`