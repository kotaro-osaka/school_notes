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
- **Performance:** Excellent read/write
- **Redundancy:** Survives one failure per mirrored pair
- **Min drives:** 4
- **Use case:** Databases, high-traffic applications

### RAID 01 (0+1) - Stripe then Mirror
- Drives striped first into groups, then those stripes are mirrored
- **Performance:** Excellent read/write (similar to RAID 10)
- **Redundancy:** Weaker than RAID 10 - if one drive in a stripe fails, the entire stripe is lost; one more failure anywhere kills the array
- **Min drives:** 4
- **Use case:** Rarely preferred over RAID 10; sometimes seen in older hardware controllers

> **RAID 10 vs 01:** Both use the same number of drives and capacity, but RAID 10 is generally more resilient. In a 4-drive RAID 10, you can lose one drive from each mirror pair (2 drives total). In RAID 01, a single drive failure degrades a whole stripe, leaving only the one remaining mirror — any second failure is catastrophic.

### RAID 50 (5+0) - RAID 5 Arrays Striped
- Multiple RAID 5 groups striped together
- **Performance:** Better read/write than plain RAID 5, scales well
- **Redundancy:** Each RAID 5 group tolerates 1 failure; if 2 drives fail in the same group, all data is lost
- **Min drives:** 6 (two groups of 3)
- **Use case:** Large enterprise storage, high-throughput file servers, video production

## Comparison

| Level | Min Drives | Fault Tolerance    | Speed | Usable Capacity |
| ----- | ---------- | ------------------ | ----- | --------------- |
| 0     | 2          | None               | ⚡⚡⚡   | 100%            |
| 1     | 2          | 1≤ drives          | ⚡⚡    | 50%             |
| 5     | 3          | 1 drive            | ⚡⚡    | (n-1)/n         |
| 6     | 4          | 2 drives           | ⚡     | (n-2)/n         |
| 01    | 4          | 1 drive            | ⚡⚡⚡   | 50%             |
| 10    | 4          | 1 per mirror pair  | ⚡⚡⚡   | 50%             |
| 50    | 6          | 1 per RAID 5 group | ⚡⚡⚡   | (n-groups)/n    |
