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
    - `'%'` → von beliebigen Hosts / IP-Adressen
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
- **`PASSWORD('wert')`**: Verschlüsselt das Passwort intern in MySQL (==Veraltet==)
- MySQL-Versionen (8+):

```sql
ALTER USER 'benutzername'@'host' IDENTIFIED BY 'passwort';
```

### Berechtigungen zuteilen

```sql

```