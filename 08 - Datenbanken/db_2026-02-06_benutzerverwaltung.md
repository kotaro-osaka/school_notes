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

- **`CREATE USER`**: Erstellt einen neuen MySQL/MariaDB-Benutzer.
- **`'benutzername'`**: Name des Benutzers
    
- **`'host'`**: Gibt an, von wo der Benutzer sich verbinden darf:
    
    - `'localhost'` → nur vom lokalen Rechner (wo die Datenbank läuft)
        
    - `'%'` → von beliebigen Hosts / IP-Adressen
        
    - `'192.168.1.%'` → Beispiel für ein ganzes Subnetz