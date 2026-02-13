# Benutzerrechte
___
## Aufgabe 1
- Geschäftsführer -> `role_management`
- Personalabteilung -> `role_hr`
- Buchhaltung -> `role_accounting`
- Projektmanager -> `role_project_manager`
- Entwickler -> `role_developer`
- Vertriebsmitarbeiter -> `role_sales`
- Externe Praktikanten -> `role_intern`
## Aufgabe 2

| Rolle                | mitarbeiter                            | kunden                                 | projekte                               | rechnungen                             |
| -------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| role_management      | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| role_hr              | `SELECT`, `INSERT`, `UPDATE`           | -                                      | -                                      | -                                      |
| role_accounting      | `SELECT`                               | `SELECT`                               | `SELECT`                               | `SELECT`, `INSERT`, `UPDATE`           |
| role_project_manager | `SELECT`                               | `SELECT`                               | `SELECT`, `INSERT`, `UPDATE`           | -                                      |
| role_developer       | `SELECT`                               | -                                      | `SELECT`, `UPDATE`                     | -                                      |
| role_sales           | -                                      | `SELECT`, `INSERT`, `UPDATE`           | `SELECT`                               | `SELECT`                               |
| role_intern          | -                                      | -                                      | `SELECT`                               | -                                      |
## Aufgabe 3
### Rollen anlegen
```sql
CREATE ROLE role_management;
CREATE ROLE role_hr;
CREATE ROLE role_accounting;
CREATE ROLE role_project_manager;
CREATE ROLE role_developer;
CREATE ROLE role_sales;
CREATE ROLE role_intern;
```

### Benutzer anlegen
```sql
CREATE USER 
```