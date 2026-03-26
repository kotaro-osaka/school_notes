# Datensicherungsverfahren
___
**Gegeben:**
- Anfangsdatenbestand: `50 GiB`
- Tägliche Erhöhung: `500 MiB`
- Ausfallsicherheit: `30 Tage`

## Aufgabe 1 - Speicherbedarf
> Tag 30: $50 + 29 \cdot 0,5 =$ `64,5 GiB`

**Vollbackup:**
- Tägliche Speicherung des kompletten Bestands
	=> $30 \cdot 50 + 0,5 \cdot \frac{29 \cdot 30}{2} =$ `1717,5 GiB`

**Inkrementelles Backup:**
- 1x Vollbackup an Tag 1: `50 GiB`
- 29x tägliche Änderung: je `0,5 GiB` → $29 \cdot 0,5=$ `14,5 GiB`
	=> $50 + 14,5=$ `64,5 GiB`

**Differenzielles Backup:**
- 1x Vollbackup an Tag 1: `50 GiB`
- Speichert die Änderungen seit dem letzten Vollbackup
	=> $30 \cdot 50 + 0,5 \cdot \frac{29 \cdot 30}{2}=$ `1717,5 GiB`

## Aufgabe 2 - Speicherbedarf bei wöchentlichem Zyklus
**Gegeben:**
- 4 vollständige Wochen + Rest => 5 Vollbackups um 30 Tage abzudecken

| Vollbackup | Tag | Bestand  |
| ---------- | --- | -------- |
| 1          | 1   | 50,0 GiB |
| 2          | 8   | 53,5 GiB |
| 3          | 15  | 57,0 GiB |
| 4          | 22  | 60,5 GiB |
| 5          | 29  | 64,0 GiB |

*Geht man davon aus, dass Backups älter als 5 Wochen überschrieben werden*

**Vollbackup:**
$$50 + 53,5 + 57 + 60,5 + 64 = 285 GiB$$

**Inkrementelles Backup:**
$$(50 + 53,5 + 57 + 60,5 + 64) + 5 \cdot 3 = 300 GiB$$

**Differenzielles Backup:**
Pro Zyklus:
- 1 Vollbackup
- Akkumulierende Differenzen ($0,5 + 1,0 + 1,5 + 2,0 + 2,5 + 3,0 = 10,5 GiB$)
$$285 + 5 \cdot 10,5 = 337,5 GiB$$
