# $I^2C Protokoll$
___
## Arduino
> src: https://docs.arduino.cc/learn/communication/wire/

> "Inter-integrated circuit protokoll"
> Wird von allen Arduino Boards unterstützt 

### Peripherie
- Sensoren, Displays, Motortreiber? (motor drivers), etc.
- Können mit wenigen Kabeln verbunden werden
	- Flexibilität, schnelleres Prototyping
- Kommunikation mit bis zu 128 Teilnehmern

### Aufbau
#### Senden & Empfangen:
- SCL (serial clock pin): Arduino sendet regelmäßig Taktimpulse darüber
- SDA (serial data pin): Datenaustausch
- Ein Controller-Gerät mit mind. einem Peripheriegerät

![[et_i2c_aufbau.png.png|500]]
**Teilnehmer**:
> - Master & Slaves
> - Bsp: Master=Controller, Slave=Display
> - Mehrere Master=Multi-Master-Bus
> - Max 127 Slaves
> - Alle verwenden den gleichen Bustakt=Synchroner Bus
### Datenaustausch
- Serielle Datenübertragung
	- Daten werden hintereinander über eine Leitung gesendet
	- I2C-Bus definiert den Ablauf davon

1. 1Bit-Transfer bei Clock Änderung von LOW auf HIGH (von board zu I2C über SDA)
2. Datenübertragung verläuft solange, bis 7 Bit Adresse (des jeweiligen Geräts) + 1Bit (read oder write) und Befehl/Daten geformt sind
3. Aufgerufene Geräte senden wenn nötig Daten über SDA zurück
(Prompt)

- Jedes Gerät besitzt eine eigene einzigartige Adresse
- Datenpakete bestehen aus Adresse des Geräts (an das das Paket gesendet wird) und die zu übertragenden Daten
- Durch die Einzigartigkeit jedes Geräts mit Adresse können Daten abwechselnd über die gleiche Leitung gesendet werden

![[et_i2c_message.png|500]]
1. Adresse wird angegeben, damit das passende Gerät zuhört (7Bit)
2. 1 weiteres Bit zur Angabe, ob das Gerät in Read oder Write modus versetzt werden soll gesendet
3. Empfänger sendet Bestätigung, um unerwartete Ergebnisse zu vermeiden
4. Nach der Bestätigung kann der Controller mit dem nächsten Datenpaket fortfahren 
5. (8 Bit Daten)
6. Nach jedem Datenpaket wird eine Bestätigung an den Controller gesendet, um ihn fortfahren zu lassen

- Korrekte Unterscheidung zwischen Anfang und Ende der Adressen, Nachrichten, etc. wird durch die Synchronisierung der Clock ermöglicht

- Empfangendes Gerät bestimmt durch das Acknowledge-Bit (Bestätigung), ob es weitere Datenpakete empfangen kann
- Fehlendes Acknowledge-Bit bedeutet, dass keine weiteren Daten empfangen werden können oder, dass eine neue Adresse folgt

**Wire Bibliothek**: [link](https://docs.arduino.cc/learn/communication/wire/#wire-library)
**2 Arduinos verbinden**: [link](https://docs.arduino.cc/learn/communication/wire/#controller-writer)

### Datenerfassung
- SCL & SDA sind standardmäßig auf HIGH (keine Kommunikation)
- Start-condition: Während SCL auf HIGH ist, wechselt SDA auf LOW
- End-condition: Während SCL auf LOW ist, wechselt SDA auf HIGH
