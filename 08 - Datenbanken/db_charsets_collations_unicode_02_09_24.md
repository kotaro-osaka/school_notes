# Character Sets, Collations, Unicode
___
- Dienen zur Speicherung von Daten in verschiedenen Zeichensätzen
- Vergleiche werden mithilfe von Vorgaben des Collations durchgeführt
- **Default**: `utf8mb4`, `utf8mb4_0900_ai_ci` (*wird nach Möglichkeit empfohlen)
- Character Sets können auf **Server**-, **Datenbank**-, **Tabellen**-, **Spalten**- und **String-Literal-Ebene** angegeben werden
- `UTF8` ist ein abgewertetes Synonym für `utf8mb3` (*wird in Zukunft entfernt*)
- Character Set Probleme haben Auswirkungen auf Datenspeicherung und Kommunikation zwischen Client und MySQL Server

> [!info]
> Wenn Client und Server miteinander kommunizieren sollen und der Client einen anderen Charset verwendet als der Server, muss folgender Befehl nach Verbindung mit dem Server ausgeführt werden:
> `SET NAMES 'utf8mb4';`
## Was sind Character Sets und Collations?
___
- **Charsets** sind Mengen von Symbolen und Kodierungen
- **Collations** sind Mengen von Regeln zum Vergleichen von Zeichen in einem Charset

> [!info] Beispiel
> Buchstaben sind **Symbole**, Zahlen sind **Kodierungen**:
> `A=0`, `B=1`,`a=2`, `b=3` 
> Kombinationen aller Buchstaben und Kodierungen nennt man **Zeichensatz**.
> Der einfachste Weg, `A` und `B` zu vergleichen besteht darin, die Kodierungen zu vergleichen (`0` und `1`), daraus folgt, dass `A` kleiner ist als `B`.
> Dies versteht man unter der Anwendung einer Collation.

**MySQL Optionen**:
- Strings in verschiedenen Charsets speichern
- Strings mit verschiedenen Collations vergleichen
- Strings mit verschiedenen Charsets oder Collations im selben Server, der selben Datenbank oder Tabelle mischen
- Spezifikationen von Charsets und Collations auf jeder Ebene aktivieren

**Verfügbare Charsets ausgeben**:
- `INFORMATION_SCHEMA_CHARACTER_SETS` Tabelle
- `SHOW CHARACTER SET` Befehl

- Charsets haben immer mindestens eine Collation

**Verfügbare Collations ausgeben**:
- `INFORMATION_SCHEMA_COLLATIONS` Tabelle
- `SHOW COLLATION` Befehl

### Charakteristiken von Collations
___
1. 2 Charsets können nicht die selbe Collation haben
2. Jedes Charset hat eine *default Collation* (können in `INFORMATION_SCHEMA_CHARACTER_SETS` Tabelle oder mit `SHOW CHARACTER SET` Befehl eingesehen werden)
3. Collation-Namen beginnen mit dem Namen des dazugehörigen Charsets, darauf folgt ein oder mehrere Suffixe, die auf andere Collation Charakteristiken hinweisen
## Stringrepertoire
___
*Das Repertoire eines Strings ist die Sammlung der Zeichen im Satz*
- Stringausdrücke haben ein *Repertoireattribut*, das 2 Werte haben kann:
	- `ASCII`: Ausdruck darf nur ASCII-Zeichen enthalten
	- `UNICODE`: Ausdruck kann Zeichen im Unicode-Bereich `U+0000`-`U+10FFFF` enthalten
- `ASCII`-Bereich ist eine Teilmenge von `UNICODE`-Bereich
	- Strings mit `ASCII`-Repertoire können ohne Informationsverlust sicher in den Charset einer beliebigen Zeichenfolge mit `UNICODE`-Repertoire konvertiert werden 
# Quellen
___
https://dev.mysql.com/doc/refman/8.4/en/charset.html