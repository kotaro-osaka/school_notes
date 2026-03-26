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
