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
- **Maximal** (größtes Vollbackup=Tag 29): `64 GiB = 65.536 MiB` → $65.536 \div 119,2 ≈ 550s ≈$ `9,2 min`

**Inkrementelles Backup:**
Alle Bänder seit dem letzten Vollbackup werden benötigt
- **Minimal** (bester Fall=direkt nach Vollbackup, nur 1 Band): $53,5 GiB \div 119,2 MiB/s \approx 459s \approx$ `7,7 min`
- **Maximal** (schlechtester Fall=letzter Tag des Zyklus, 7 Bänder): $64 GiB + 6 \cdot 0,5 GiB =$ `67 GiB` → $68.608 MiB \div 119,2 \approx 576s \approx$ `9,6 min`

**Differenzielles Backup:**
Immer Vollbackup + 1 differenzielles Backup
- **Minimal** (Tag direkt nach Vollbackup): $53,5 + 0,5 = 54 GiB$ → $55.296 MiB \div 119,2 \approx 464s \approx$ `7,7 min`
- **Maximal** (letzter Tag des Zyklus): $64 + 3 = 67 GiB$ → $68.608 MiB \div 119,2 \approx 576s \approx$ `9,6 min`

## Aufgabe 4 - Bewertung
**Vollbackup:**
- Sehr einfache Wiederherstellung (1 Medium)
- Enormer Speicherbedarf (`1717,5 GiB` täglich)
- Langer Sicherungsaufwand
- Für Datenbank mit starkem Wachstum **nicht Empfehlenswert**

**Inkrementelles Backup:**
- Geringster Speicherbedarf (`64,5 GiB` täglich)
- Schnelle Sicherung da nur Änderungen gespeichert werden
- Wiederherstellung ist komplex und fehleranfällig - alle Bänder müssen vorhanden sein
- **Gut für Speichereffizienz, riskant bei Wiederherstellung**

**Differenzielles Backup:**
- Nur Vollbackup + ein differenzielles Band für Wiederherstellung
- Robuster als inkrementell
- Moderater Speicherbedarf (`267,5 GiB` täglich)
- **Empfehlenswert**, da Wiederherstellung zuverlässig und schnell ist

**Empfehlung:**
- Differenzielles Backup
- Wöchentlicher Vollbackup-Zyklus

## Expertenaufgabe - Formel herleiten
**Gegeben:**
- $D=$ Anfangsdatenbestand in `GiB`
- $z=$ Zuwachs pro Tag in `MiB` $=z/1024 GiB$
- $T=$ Zeitraum in Tagen
### Vollbackup
$$S=T \cdot D + \frac{z \cdot T(T-1)}{2048}[GiB]$$
### Inkrementelles Backup
$$S=D + \frac{z(T-1)}{1024}[GiB]$$
### Differenzielles Backup
$$S=D + \frac{z \cdot T(T-1)}{2048}[GiB]$$
