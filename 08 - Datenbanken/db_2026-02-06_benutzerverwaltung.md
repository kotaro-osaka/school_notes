# Benutzerverwaltung
___
## Rollen
- Admin
## Rechte
- `SELECT`
- `INSERT`
- `UPDATE`
- `DELETE`

## SQL-Syntax
### Benutzer erstellen

```sql
CREATE USER 'benutzername'@'host';
```

- **`CREATE USER`**: Erstellt einen neuen MySQL/MariaDB-Benutzer
- **`'benutzername'`**: Name des Benutzers
- `@`: Trennzeichen
- **`'host'`**: Gibt an, von wo der Benutzer sich verbinden darf:
    - `'localhost'` → nur vom lokalen Rechner (wo die Datenbank läuft)
    - `'%'` → von beliebigen Hosts / IP-Adressen (“Wildcard“)
    - `'192.168.1.%'` → Beispiel für ein ganzes Subnetz

Beispiele:
```sql
CREATE USER 'root_localhost'@'localhost';
CREATE USER 'root_ip'@'%';
```

- `root_localhost` darf sich nur lokal verbinden
- `root_ip` darf sich von überall verbinden

### Passwörter festlegen

```sql
SET PASSWORD FOR 'benutzername'@'host' = PASSWORD('passwort');
```

- **`SET PASSWORD FOR`**: Legt Passwort für einen vorhandenen Benutzer fest
- **`PASSWORD('wert')`**: Verschlüsselt das Passwort intern in MySQL (==Depricated==)
- MySQL-Versionen (8+):

```sql
ALTER USER 'benutzername'@'host' IDENTIFIED BY 'passwort';
```

### Berechtigungen zuteilen

```sql
GRANT rechte ON datenbank.tabelle TO 'benutzername'@'host';
```

- **`rechte`**: Welche Operationen erlaubt sind:
    - `ALL PRIVILEGES` → Alle Rechte (SELECT, INSERT, UPDATE, DELETE, etc.)
    - Einzelne Rechte z.B. `SELECT`, `INSERT`, `UPDATE`, `DELETE`
- **`datenbank.tabelle`**:
    - `*.` → Alle Datenbanken
    - `*` → Alle Tabellen
    - `fahrschule.*` → Alle Tabellen der Datenbank `fahrschule`
    - `fahrschule.fahrschueler` → Nur diese Tabelle
- **`TO 'benutzername'@'host'`**: Wer Rechte bekommt

Beispiele:
```sql
GRANT ALL PRIVILEGES ON *.* TO 'root_localhost'@'localhost';

GRANT SELECT, INSERT ON fahrschule.fahrstunden TO 'fahrlehrer'@'%';

GRANT SELECT (kfznr, kennzeichen, typ, marke) ON fahrschule.kfz TO 'fahrschueler'@'%';
```

- `root_localhost` → Vollzugriff auf alle Datenbanken
- `fahrlehrer` → Darf nur in `fahrstunden` lesen und schreiben, sowie `fahrschueler` lesen
- `fahrschueler` → Darf nur bestimmte Spalten (`kfznr, kennzeichen, typ, marke`) der Tabelle `kfz` lesen

**Man kann Rechte auf einzelne Spalten beschränken:**
```sql
GRANT SELECT (splate1, spalte2) ON db.tabelle TO 'benutzer'@'host';
```

(Nützlich, wenn persönliche Daten geschützt werden sollen)

### Änderungen wirksam machen

```sql
FLUSH PRIVILEGES;
```

- MySQL speichert Berechtigungen im Speicher für Performance
- Nach Änderungen (Benutzer erstellen, Rechte ändern) sorgt `FLUSH PRIVILEGES` dafür, dass MySQL die Änderungen sofort übernimmt
- **Moderne MySQL-Versionen:** Bei Verwendung von `CREATE USER` / `GRANT` automatisch, also oft nicht nötig

### Benutzer löschen
```sql
DROP USER 'benutzername'@'host';
```

- **`DROP USER`**: Entfernt einen Benutzer aus der Datenbank komplett
- **`'benutzername'`**: Name des Benutzers, der gelöscht werden soll
- **`'host'`**: Muss genau der Host sein, der bei `CREATE USER` angegeben wurde

Beispiele:
```sql
DROP USER 'root_localhost'@'localhost';
DROP USER 'fahrschueler'@'%';
```

- `root_localhost` wird nur vom lokalen Rechner gelöscht
- `fahrschueler` wird überall gelöscht, weil er sich von allen Hosts verbinden darf (`'%'`)

### Berechtigungen entziehen

```sql
REVOKE rechte ON datenbank.tabelle FROM 'benutzername'@'host';
```

- **`REVOKE`**: Entzieht einem Benutzer bestimmte Rechte, die vorher mit `GRANT` vergeben wurden
- **`rechte`**: Welche Rechte entzogen werden sollen (z. B. `SELECT`, `INSERT`, `UPDATE`, `DELETE`, oder `ALL PRIVILEGES`)
- **`datenbank.tabelle`**:
    - `*.*` → Alle Datenbanken und Tabellen
    - `fahrschule.*` → Alle Tabellen der Datenbank `fahrschule`
    - `fahrschule.fahrschueler` → Nur diese Tabelle
- **`FROM 'benutzername'@'host'`**: An welchen Benutzer das Entziehen erfolgt

