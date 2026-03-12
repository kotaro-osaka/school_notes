# Übungsklausur
___
## 1.1
Gegeben:
- 4 IP-Kameras
- RJ45
- 10/100 MBit/s

Switch mit 4 Ports (100 MBit/s) wird mit bestehenden Switch in Verkaufshalle verbunden

## 1.2 - Datenmenge pro Sekunde (eine Kamera)
Gegeben:
- Motion JPEG: 1 Bit/Pixel
- MPEG4: 0,5 Bit/Pixel
- H264: 0,2 Bit/Pixel
- MPEG 2: 0,52 Bit/Pixel

Geringstmögliche Datenmenge => H.264 (0,2 Bit/Pixel)

**Rechnung:**

| Schritt             | Rechnung                               | Ergebnis           |
| ------------------- | -------------------------------------- | ------------------ |
| Pixel pro Bild      | $752 \times 582$                       | $=437.664$ Pixel   |
| Bits pro Bild       | $437.664 \times 0,2 Bit$               | $=87.532,8$ Bit    |
| Bits pro Sekunde    | $87.532,8 \times 25$                   | $=2.188.320$ Bit/s |
| Umrechnung in MiB/s | $2.188.320 \div 8 \div 1024 \div 1024$ | $≈0,261$ MiB/s     |
**≈ 0,261 MiB/s**

## 1.3 - Festplattenspeicherkapazität für 30T

| Schritt     | Rechnung              | Ergebnis            |
| ----------- | --------------------- | ------------------- |
| 4 Kameras/s | $0,261 \times 4$      | $=1,044$ MiB/s      |
| Pro Minute  | $\times 60$           | $=62,64$ MiB/min    |
| Pro Stunde  | $\times 60$           | $=3.758,4$ MiB/h    |
| Pro Tag     | $\times 24$           | $=90.201,6$ MiB/Tag |
| 30 Tage     | $\times 30$           | $=2.706.048$ MiB    |
| In TiB      | $\div 1024 \div 1024$ | $≈2,58$ TiB         |
Festplatte muss mind. **≈2,58 TiB** groß sein

## 1.4 - Subnetting
Gegeben:
- Server: 192.168.20.125/27 

**Rechnung:**
1. `/27` = `255.255.255.224`
2. `224` = `111 00000`
3. `125` = `011 11101`
4. Netzadresse = `192.168.20.96`
5. Broadcastadresse = `192.168.20.127`
6. Nutzbare Hosts = $2^5-2=$ `30`

## 1.5 - VLAN
Kameras und Server ohne Neuverkabelung vom restlichen Netz trennen:
- Sicherstellen, dass Switch VLAN-fähig ist
- VLAN 1: Büronetzwerk
- VLAN 2: Kameranetzwerk
- Ports der Kameras und Server zuweisen
- Kommunikation zwischen VLANs nur über Router/L3-Switch möglich
	=> Trennung ohne Neuverkabelung

## 2.1 - Vorteile WLAN vs. Kabel
1. Keine Verkabelung notwendig → Spart Installations- & Materialkosten
2. Flexible Aufstellung der Infosäulen
3. Schnellere Installation

## 2.2 - Signalstärke
- Signalstärke nimmt mit zunehmender Entfernung ab
- Schwächung durch Hindernisse → Übertragungsfehler
	- Fehler kompensieren durch niedrigere Modulationsrate (starke Reduzierung d. Nettodatenrate)
- Overhead steigt durch Wiederholungsübertragungen

## 2.3 - Lösungsvorschlag
- Mehrere Accesspoints
- Infosäulen näher am Accesspoint positionieren
- Kabel (zuverlässiger & schneller)

## 2.4 - SSID
- SSID-Broadcast deaktivieren

## 2.5 - Ad-hoc
- Verbindung über WLAN als Peer-to-Peer-WLAN = **Ad-hoc-Modus**

## 3.1 - Datensicherheit
**Datenintegrität:**
- Übertragene Daten bleiben auf dem Weg zwischen Sender → Empfänger *unverändert* und können *nicht manipuliert* werden
	=> Prüfsummen (Hashwerte)

**Vertraulichkeit:**
- Daten können nur von berechtigten Empfängern während der Übertragung gelesen werden
	=> Verschlüsselte Übertragung

**Authentisierung:**
- Nur berechtigte Nutzer dürfen Zugang erhalten

## 3.2 - Authentisierungsverfahren
b) Radius-Server
=> individuelle, zeitbegrenzte Authentisierung pro Nutzer

## 3.3 - Verschlüsselungsverfahren
a) WPA: mittlere Sicherheit (TKIP) - gilt als unsicher
b) WPA2: hohe Sicherheit (AES) - gilt als sicher
c) WEP: sehr geringe Sicherheit - gilt als unsicher & veraltet

## 3.4 - Manipulation erkennen
**Integritätsprüfung:**
- Hashwerte (Message Digest) einsetzen
- Vor Übertragung aus Datenpaket (Gebot) Hashwert berechnen & mit Daten übertragen
- Empfänger berechnet nach Empfang erneut Hashwert & vergleicht mit mitgesendeten Wert

## 3.5 - MIMO-Technologie
> Multiple Input Multiple Output
- Nutzt **mehrere Antennen gleichzeitig** zum Senden & Empfangen

Vorteile:
- Höhere Datenrate (mehrere Datenströme)
- Stabilere Verbindung (Mehrwegausbreitung)

## 4.1 - Maßnahmen zum Schutz
- **Zugangsschutz:** Serverraum abschließen, Zugang nur für befugte
- **Authentifizierung:** Passwortschutz, Benutzerverwaltung mit sicheren Passwörtern
- **Firewall:** Schutz vor unberechtigten Netzwerkzugriffen
- **Virenschutz:** Aktuelle Antivirensoftware installieren & regelmäßig aktualisieren
- **Regelmäßige Updates:** Betriebssystem & Software aktuell halten, um Sicherheitslücken zu schließen
- **USV:** Schutz vor Datenverlust durch Stromausfall

## 4.2 - Alte Datenträger
> Personenbezogene Daten müssen sicher & unwiederbringlich vernichtet werden
- Physische Zerstörung des Datenträgers
- Zertifiziertes Überschreiben mit Software

## 4.3 - RAID
> 5 Festplatten, Ausfall einer Festplatte + Max. Speicherkapazität

**RAID 5:**
- Benötigt mind. 3 Festplatten
- Kann Ausfall von 1 Festplatte kompensieren
- Parität
- Nutzbare Kapazität: $(5-1) \times 4 TiB=16 TiB$

## 4.4 - 