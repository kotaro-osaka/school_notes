# Benutzerverwaltung Befehle
___
```mysql
-- Rolle erstellen: 
CREATE ROLE admin; (CREATE ROLE mitarbeiter; usw.)

-- User erstellen: 
CREATE USER "mueller"@"localhost" IDENTIFIED BY "Passwort123";

Usern Rollen zuweisen: 
GRANT mitarbeiter TO "mueller"@"localhost";

Rechte zuweisen: 
GRANT SELECT ON Beispieldatenbank.Beispieltabelle TO mitarbeiter;

Aktivierung der Benutzerrechte: 
FLUSH PRIVILEGES;

Löschen von Rollen: 
DROP admin; usw
```