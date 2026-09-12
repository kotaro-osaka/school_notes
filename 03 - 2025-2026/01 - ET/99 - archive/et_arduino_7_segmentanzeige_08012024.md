# Hinweise zur Ansteuerung der 7-Segmentanzeige
- 16 Bit an Daten (8 Bit pro Ziffer)
- `SCLK`: Serial Clock
- `SDI`: Serial Data Input
- `LOAD`: Anzeige der Ziffer
	- LOAD -> Low
	- SCLK -> Low
	- SDI -> ?
	- SCLK -> HIGH
	- LOAD -> HIGH