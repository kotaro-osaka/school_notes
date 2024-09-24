# RGB LED
___
## Aufbau
![[Screenshot 2024-01-26 094611.png]]
- 4 Beine:
	- Rot
	- Kathode (längstes Bein; wird mit GND verbunden)
	- Grün
	- Blau
- Widerstände:
	- Rot: $~6,8kΩ$
	- Grün/Blau: $~10kΩ$

**Pulse Width Modulation (PWM)**
- Simuliert Analoges Signal
- Wird von Pins mit dem Symbol `~` unterstützt
- Sendet Impulse
	- Je häufiger Impulse gesendet werden, desto heller wird die LED
- Wird zusammen mit AnalogWrite-Funktion verwendet
## Schaltplan
![[Pasted image 20240126093925.png]]
## Ablauf
- Rot-/Grün-/Blautöne zwischen 0 und 255

1. Zufälliger Wert zwischen 0 und 255 wird jeweils für Rot, Grün und Blau generiert
2. Werte werden an LED gesendet