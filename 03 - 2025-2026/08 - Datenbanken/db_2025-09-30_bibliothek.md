# Bibliothek
___
1. Wieso ist diese Tabelle anfällig für Anomalien?
	1. Nicht atomar (Redundanzen)
2. Wo kann es bei welcher Operation Probleme geben? (Insert, Update, Delete)
	1. Neue Daten können nicht hinzugefügt werden, ohne nicht-verwandte Daten einzutragen
	2. Redundante Daten werden an einem Ort aktualisiert, aber nicht an anderen, wodurch inkonsistente Informationen auftreten
	3. Das Löschen von Daten löscht unabsichtlich andere Daten mit, die noch gebraucht werden
3. Erstelle ein ERD zu der Tabelle
	1. Buch
	2. (Autor)
	3. Buch_Autor (ZT für Ausleihdatum)
	4. Verlag
	5. Ausleiher
	6. Ort
4. Wandel das ERD in Relationen um.
5. Prüfe, ob sich das ERD in der 3. Normalform befindet.
6. Erstelle eine Datenbank “Bibliothek” und implementiere die Tabellen “Buch” und “Verlag”