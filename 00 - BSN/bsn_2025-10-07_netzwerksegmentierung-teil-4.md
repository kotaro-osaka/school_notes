# Netzwerksegmentierung Teil 4
___
## Aufgabe 1
> Wie lautet die Subnetzmaske des ungeteilten Netzwerks `172.23.0.0/16`?

`255.255.0.0`

## Aufgabe 2
1. Neue Subnetzmaske: `255.255.192.0` / `/18` ($2^2$)
2. Netzwerk- & Broadcastadressen
	1. `172.23.0.0`; `172.23.63.255`
	2. `172.23.64.0`; `172.23.127.255`
	3. `172.23.128.0`; `172.23.191.255`
	4. `172.23.192.0`; `172.23.255.255`
3. Adressen zuteilen
	1. Blau
		1. Router `172.23.0.1`
		2. Server `172.23.0.2`
	2. Grün
		1. Router `172.23.64.1`
		2. PC `172.23.64.2`
		3. PC `172.23.64.3`
		4. PC `172.23.64.4`
		5. PC `172.23.64.5`
	3. Rot
		1. Router `172.23.128.1`
		2. PC `172.23.128.2`
		3. PC `172.23.128.3`
		4. PC `172.23.128.4`
		5. PC `172.23.128.5`