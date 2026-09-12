**21.08.2023**

- Isolationswiderstandtest I: (R<sub>ISO</sub>)
- 1 MΩ auf 1    
- 299 MΩ auf 2
- IEA 0,01 mA  Auf 2


**23.08.2023**
### Erstellen Sie ein Flussdiagramm, nach dem Sie die Messungen nach VDE 0701 und VDE 0702 durchführen können.

```mermaid
flowchart TD
	A(Start)
	B{Sichtprüfung<br>Sichtbare Mängel?}
	C{Gefahren bei<br>bestimmungs-<br>gemäßen<br>Gebrauch?}
	D{Schutzleiter vorhanden?}
	E[Schutzleiter-<br>widerstand<br>messen]
	F[Schutzleiterstrom<br>messen]
	G{Isolationsmessung<br>durchführbar?}
	H[Isolations-<br>widerstand<br>messen]
	I[Berührungs<br>-strom<br>messen]


	
	
	L[Prüfung einstellen,<br>Gerät als<br>fehlerhaft markieren<br>und<br>Betreiber darüber<br>informieren]
	M(Nicht Bestanden)
	
	A --> B
	B -->|Nein| C
	B -->|Ja| O
	
	C -->|Nein| D
	C -->|Ja| M
	
	D -->|Ja| E
	D -->|Nein| G
	
	E -->|unter<br>0,3Ω| F
	E -->|über<br>0,3Ω| M
	
	F -->|über<br>3,5mA| M
	F -->|unter<br>3,5mA| G
	
	G -->|nein| M
	G -->|ja| H
	
	H --> I
	
	I -->|Nein| K
	I -->|Ja| J
	
	J -->|Nein| M
	J -->|Ja| N
	
	K --> L
	
	L -->|Nein| M
	L -->|Ja| L
	
	M --> M
	N --> M
	
	O --> M
```



I{Berührbare leitfähige<br>Teile, die nicht<br>mit PE verbunden<br>sind?}
	J[Messung des<br>Berührungsstromes]
	K[Messung des<br>Ersatz-Ableitstroms]