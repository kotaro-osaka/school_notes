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
- Akkumulierende Differenzen ($0,5 + 1,0 + 1,5 + 2,0 + 2,5 + 3,0 = 10,5 GiB \text{ pro Zyklus}$)
$$285 + 5 \cdot 10,5 = 337,5 GiB$$

## Aufgabe 3 - Rücksicherungszeit
**Gegeben:**
- Netzwerkverbindung: `1000 MBit/s`
- Rücksicherung stellt letzten vollständig gesicherten Stand wieder her

**Vollbackup:**
Immer nur ein Vollbackup nötig.
- **Minimal** (kleinstes Vollbackup=Tag 1): `50 GiB = 51.200 MiB` → $51.200 ÷ 119,2 ≈ 429s ≈$ `7,2 min`
- **Maximal** (größtes Vollbackup=Tag 29): `64 GiB = 65.536 MiB` → $65.536 ÷ 119,2 ≈ 550s ≈$ `9,2 min`

**Inkrementelles Backup:**
Alle Bänder seit dem letzten Vollbackup werden benötigt
- **Minimal** (bester Fall=direkt nach Vollbackup, nur 1 Band): $53,5 GiB ÷ 119,2 MiB/s ≈ 459s ≈$ `7,7 min`
- **Maximal** (schlechtester Fall=letzter Tag des Zyklus, 7 Bänder): $64 GiB + 6 \cdot 0,5 GiB =$ `67 GiB` → 68.608 MiB