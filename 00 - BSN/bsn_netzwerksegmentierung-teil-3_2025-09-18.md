# Netzwerksegmentierung
___
## Aufgabe 1
Gegeben
- **Netzadresse**: `192.168.35.0`
- **Subnetzmaske**: `255.255.255.0`
Gebraucht
- 6 Subnetze
### a) Wie lautet die Subnetzmaske?
- `255.255.255.224`
- `/27`
### b) Wie viele Subnetze werden durch die Subnetzmaske erzeugt?
→ $2^3=8$ Subnetze
### c) Gebe die Netzadressen aller verfügbaren Subnetze in CIDR-Darstellung an.
1. `192.168.35.0/27` (`.000`)
2. `192.168.35.32/27` (`.001`)
3. `192.168.35.64/27` (`.010`)
4. `192.168.35.96/27` (`.011`)
5. `192.168.35.128/27` (`.100`)
6. `192.168.35.160/27` (`.101`)
7. `192.168.35.192/27` (`.110`)
8. `192.168.35.224/27` (`.111`)
### d) Gebe die Anzahl nutzbarer Hostadressen pro Subnetz an.
- **Differenz Bits**: $32-27=5$ Hostbits
- $2^5=32$ Adressen pro Subnetz
- $32-2=30$ Nutzbare Adressen pro Subnetz
### e) Gebe für jedes Subnetz die Broadcastadresse an.
1. `192.168.35.31` (`.00011111`)
2. `192.168.35.63` (`.00111111`)
3. `192.168.35.95` (`.01011111`)
4. `192.168.35.127` (`.01111111`)
5. `192.168.35.159` (`.10011111`)
6. `192.168.35.191` (`.10111111`)
7. `192.168.35.223` (`.11011111`)
8. `192.168.35.255` (`.11111111`)
### f) Gebe für jedes Subnetz die erste und letzte verwendbare IP-Adresse an.
1. `192.168.35.1` - `192.168.35.30`
2. `192.168.35.33` - `192.168.35.62`
3. `192.168.35.65` - `192.168.35.94`
4. `192.168.35.97` - `192.168.35.126`
5. `192.168.35.129` - `192.168.35.158`
6. `192.168.35.161` - `192.168.35.190`
7. `192.168.35.193` - `192.168.35.222`
8. `192.168.35.225` - `192.168.35.254`
## Aufgabe 2
Gegeben
- **Netzadresse**: `172.16.0.0`
- **Subnetzmaske**: `255.255.0.0`
Gesucht
- Mind. 6 Subnetze
- Mind. 500 Hosts pro Subnetz
### a) Bestimme die Subnetzmaske.
- $2^9=512$
	→ 9 Hostbits
	→ 512 Hosts
- $32-9=23$ Netzbits
→ `255.255.254.0`
→ `/23` (`.11111110`)
### b) Bestimme die Netzadressen der 6 Subnetze.
- $2^3=8$ Subnetze
1. `172.16.240.0` (`.11110000`)
2. `172.16.242.0` (`.11110010`)
3. `172.16.244.0` (`.11110100`)
4. `172.16.246.0` (`.11110110`)
5. `172.16.248.0` (`.11111000`)
6. `172.16.250.0` (`.11111010`)
7. `172.16.252.0` (`.11111100`) - not used
8. `172.16.254.0` (`.11111110`) - not used
### c) Bestimme die Broadcastadressen der 6 Subnetze.
1. `172.16.240.0` (`.11110001`)
2. `172.16.242.0` (`.11110010`)
3. `172.16.244.0` (`.11110100`)
4. `172.16.246.0` (`.11110110`)
5. `172.16.248.0` (`.11111000`)
6. `172.16.250.0` (`.11111010`)
7. `172.16.252.0` (`.11111100`) - not used
8. `172.16.254.0` (`.11111110`) - not used