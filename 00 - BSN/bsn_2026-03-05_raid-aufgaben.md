# RAID Aufgaben
___
- Hot-Spare: Ersatzlaufwerk, das beim Ausfall einer Platte automatisch diese ersetzt

## RAID Levels
### RAID 0 - Striping
- Data split across drives in parallel
- **Performance:** Excellent read/write
- **Redundancy:** None - one drive fails, all data lost
- **Min drives:** 2
- **Use case:** Video editing, temp data, speed-critical workloads
### RAID 1 - Mirroring
- Exact copy of data on each drive
- **Performance:** Good reads, normal writes
- **Re**