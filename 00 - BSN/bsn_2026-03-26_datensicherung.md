# Datensicherungsverfahren
___
**Gegeben:**
- Anfangsdatenbestand: `50 GiB`
- Tägliche Erhöhung: `500 MiB`
- Ausfallsicherheit: `30 Tage`

## Aufgabe 1 - Speicherbedarf
> Tag 30: $50 + 29 \cdot 0,5 = 64,5 GiB$

**Vollbackup:**
$30 \cdot 50 + 0,5 \cdot \frac{29 \cdot 30}{2} = 1717,5 GiB$

**Inkrementelles Backup:**
- 1x Voll