# VLAN Einrichten
___
## Aufgabe 1
- Port 24 ist ein Trunk-Port (Verbindet Switch mit anderen Switch)
- “Tagged”:
	- VLAN-Infos werden im Frame mitgesendet
	- Mehrere VLANs über einen Port möglich
	- Nur möglich bei Switch ←→ Switch

## Aufgabe 2
- 1000 MBit/s (Muss Verkehr aller VLANs Richtung Core-Switch bündeln - Uplink)
- Meist letzter Port

## Aufgabe 3

| Port | Speed       | Verwaltung (308) | Produktion (310) | Lager (312) | Admin (1) | Entwicklung (314) |
| ---- | ----------- | ---------------- | ---------------- | ----------- | --------- | ----------------- |
| 1    | 100 MBit/s  | No               | Yes              | No          | No        | No                |
| 2    | 100 MBit/s  | No               | No               | No          | No        | Yes               |
| 3    | 100 MBit/s  | No               | No               | No          | No        | Yes               |
| 4    | 100 MBit/s  | Yes              | No               | No          | No        | No                |
| 5    | 100 MBit/s  | Yes              | No               | No          | No        | No                |
| 6    | 100 MBit/s  | No               | No               | No          | Yes       | No                |
| …    |             |                  |                  |             |           |                   |
| 24   | 1000 MBit/s | Tagged           | Tagged           | Tagged      | Tagged    | Tagged            |
## Aufgabe 4

| Port | Speed       | Verwaltung (308) | Produktion (310) | Lager (312) | Admin (1) | Entwicklung (314) |
| ---- | ----------- | ---------------- | ---------------- | ----------- | --------- | ----------------- |
| 1    | 1000 MBit/s | Tagged           | Tagged           | Tagged      | Tagged    | Tagged            |
| 2    | 1000 MBit/s | Tagged           | Tagged           | Tagged      | Tagged    | Tagged            |
| …    |             |                  |                  |             |           |                   |
| 8    | 1000 MBit/s | Tagged           | Tagged           | Tagged      | Tagged    | Tagged            |
(Trunks)

## Aufgabe 5
1. Inter-VLAN-Routing einrichten
2. Router/L3-Switch