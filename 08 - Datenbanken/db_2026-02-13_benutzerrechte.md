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

| Rolle           | mitarbeiter                            | kunden                                 | projekte                               | rechnungen                             |
| --------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| role_management | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| role_hr         | `SELECT`, `INSERT`, `UPDATE`           | -                                      | -                                      | -                                      |
| role_accounting | `SELECT`                               | `SELECT`                               | `SELECT`                               |                                        |
