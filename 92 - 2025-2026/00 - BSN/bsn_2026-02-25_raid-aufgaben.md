# RAID Aufgaben
___
## Aufgabe 1
- JBOD = “Just a Bunch Of Disks”
- Keine Redundanz & Leistungsfähigkeit
- Platten hintereinander geschaltet (eine große logische Platte)
- Plattenausfall → Datenverlust
- RAID nutzt Striping/Mirroring/Parität (Schutz/Performance)

## Aufgabe 2

| RAID-Level | Nutzbare Kapazität | Erklärung               |
| ---------- | ------------------ | ----------------------- |
| RAID 0     | 4 TB               | Nutzung aller Platten   |
| RAID 1     | 1 TB               | Komplette Spiegelung    |
| RAID 5     | 3 TB               | Eine Platte für Parität |
- RAID 0 = $n \times \text{Größe}$
- RAID 1 = *Größe einer Platte*
- RAID 5 = $(n-1) \times \text{Größe}$

