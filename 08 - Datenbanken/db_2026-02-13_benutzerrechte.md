# Benutzerrechte
___
## Aufgabe I
- Geschäftsführer -> `role_management`
- Personalabteilung -> `role_hr`
- Buchhaltung -> `role_accounting`
- Projektmanager -> `role_project_manager`
- Entwickler -> `role_developer`
- Vertriebsmitarbeiter -> `role_sales`
- Externe Praktikanten -> `role_intern`
## Aufgabe II

| Rolle                | mitarbeiter                            | kunden                                 | projekte                               | rechnungen                             |
| -------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| role_management      | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| role_hr              | `SELECT`, `INSERT`, `UPDATE`           | -                                      | -                                      | -                                      |
| role_accounting      | `SELECT`                               | `SELECT`                               | `SELECT`                               | `SELECT`, `INSERT`, `UPDATE`           |
| role_project_manager | `SELECT`                               | `SELECT`                               | `SELECT`, `INSERT`, `UPDATE`           | -                                      |
| role_developer       | `SELECT`                               | -                                      | `SELECT`, `UPDATE`                     | -                                      |
| role_sales           | -                                      | `SELECT`, `INSERT`, `UPDATE`           | `SELECT`                               | `SELECT`                               |
| role_intern          | -                                      | -                                      | `SELECT`                               | -                                      |
## Aufgabe III
### Rollen anlegen
```mysql
CREATE ROLE
	role_management,
	role_hr,
	role_accounting,
	role_project_manager,
	role_developer,
	role_sales,
	role_intern;
```

### Benutzer anlegen
```mysql
CREATE USER 'geschaeftsfuehrer'@'localhost';
CREATE USER 'hr_mitarbeiter'@'localhost';
CREATE USER 'buchhaltung_mitarbeiter'@'localhost';
CREATE USER 'projektmanager'@'localhost';
CREATE USER 'entwickler'@'localhost';
CREATE USER 'vertriebsmitarbeiter'@'localhost';
CREATE USER 'praktikant'@'localhost';
```

### Rollen zuweisen
```mysql
GRANT role_management TO 'geschaeftsfuehrer'@'localhost';
GRANT role_hr TO 'hr_mitarbeiter'@'localhost';
GRANT role_accounting TO 'buchhaltung_mitarbeiter'@'localhost';
GRANT role_project_manager TO 'projektmanager'@'localhost';
GRANT role_developer TO 'entwickler'@'localhost';
GRANT role_sales TO 'vertriebsmitarbeiter'@'localhost';
GRANT role_intern TO 'praktikant'@'localhost';
```

## Aufgabe IV
```mysql
-- Geschäftsführer
GRANT ALL PRIVILEGES ON techsolutions.* TO role_management;

-- Personalabteilung
GRANT SELECT, INSERT, UPDATE
ON techsolutions.mitarbeiter
TO role_hr;

-- Buchhaltung
GRANT SELECT ON techsolutions.mitarbeiter TO role_
```