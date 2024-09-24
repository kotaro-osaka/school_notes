# AmNetPrime Favoritenliste
___
## 1
___
> Analysieren Sie, welche funktionalen und nicht-funktionalen Anforderungen sich aus dem obigen Szenario ergeben. Welche weiteren Punkte sind für das Pflichtenheft relevant?
### Funktionale Anforderungen
- Feste Speicherung von Lieblingsfilmen individueller Benutzer in “Favoritenliste”
- Erstellung mehrerer Listen
- Feste Anordnung der Favoriten
- Lieblingsfilme durch Referenz zwischen Existierenden Filmen in zentraler SQL-Datenbank auf `UserID` mit Kennwort kennzeichnen
- Benutzeridentifikation mit `UserID` und Kennwort
### Nicht-Funktionale Anforderungen
- Soll in den ersten Version verfügbar sein
### Weitere
- **Zielsetzung**
	- Integration einer Funktion, womit eine/mehrere Favoritenliste(n) für Benutzer in Streamingdienst “AmNetPrime” erstellt werden kann/können
## 2
___
> Sie sind es gewohnt nach einem Vorgehensmodell zu arbeiten. Entscheiden Sie sich begründet für ein Vorgehensmodell.

Ich habe mich für **Extreme Programming** (XP) entschieden, da das Lösen der Programmieraufgabe dabei in den Vordergrund gestellt wird. Dies finde ich für diese Aufgabe am passendsten, weil es darum geht einen Teilbereich des eigentlichen Projektes “AmNetPrime” nach Vorgaben zu implementieren und das Basiswissen dafür bereits besteht. Offene Fragen zur genaueren Implementation können durch kurzes Feedback  sind weitestgehend selbsterklärend und müssen sonst in der Klasse besprochen werden, was nicht durch XP ausgeschlossen ist, da Kommunikation und Feedback zu den zentralen Werten dieses Vorgehensmodells zählen.