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
- **Redundancy:** Can lose all but one drive
- **Min drives:** 2
- **Use case:** OS drives, small servers, critical data
### RAID 5 - Striping with Parity
- Data + parity spread across all drives
- **Performance:** Good reads, decent writes
- **Redundancy:** Survives 1 drive failure
- **Min drives:** 3
- **Use case:** File servers, NAS, general storage

> **How parity works:** For every chunk of data written across drives, a mathematical checksum (the parity block) is calculated and stored on a different drive. If one drive dies, the controller uses the remaining data and the parity block to reconstruct the missing data — like solving for a missing variable: if you know `A + B = C`, and you lose `A`, you can recover it from `B` and `C`. Parity rotates across all drives so no single disk becomes a bottleneck.
### RAID 6 - Striping with Double Parity
- RAID 5 but with two parity blocks
- **Performance:** Good reads, slower writes
- **Redundancy:** Survives 2 drive failure
- **Min drives:** 4
- **Use case:** Large arrays, archival, high-reliability needs
### RAID 10 (1+0) - Mirror then Stripe
- Drives mirrored in pairs first, then those mirrors are striped
- **Performance:** Excellent read/write (similar to RAID 10)
- 