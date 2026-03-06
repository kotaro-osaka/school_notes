# USV Aufgaben
___
## 2. Begriffe
- VFD: Voltage and Frequency Dependent
- VI: Voltage Independent
- VFI: Voltage and Frequency Independent

## 3. Warum kann man einen Server nicht direkt mit einer Batterie/Akku betreiben?
=> Server brauchen AC (Wechselstrom), Akkus liefern DC (Gleichstrom)
=> Begrenzte Kapazität (nicht für Dauerbetrieb geeignet)

## 4.
### VFD (Offline)
Normalbetrieb:
- Gerät wird aus der Steckdose mit Strom versorgt
- Batterie wird über den Gleichrichter mit Strom aus dem Stromnetz geladen
Notbetrieb:
- Gerät wird über den Wechselrichter mit Strom versorgt

### VI (Line-Interactive)
Normalbetrieb:
- Gerät wird über einen Spannungsregler mit Strom aus der Steckdose versorgt
- Batterie wird über den Gleichrichter mit Strom aus dem Stromnetz geladen
Notbetrieb:
- Gerät wird über den Wechselrichter mit Strom versorgt

### VFI (Online)
Normalbetrieb:
- Batterie wird über den Gleichrichter mit Strom aus dem Stromnetz geladen
- Gerät wird über den Wechselrichter mit Strom versorgt
Notbetrieb:
- Gerät wird über den Wechselrichter mit Strom versorgt

## 5.
Bei **VFD** und **VI** ist ein Umschalter verbaut.
Nachteil: Umschaltzeit (2-20 ms):
1. Ausfall erkennen
2. Umschalten
3. Wechselrichter übernimmt

## 6.
VFI hat die höchsten Stromkosten
→ Wechselrichter läuft immer

VI & VFD: Nur im Notbetrieb

## 7.
1. Spannungsunterbrechungen (Stromausfall, Kurzzeitunterbrechung)
2. Spannungsabweichungen (Unterspannung, Überspannung, Spannungsspitze/Surge, Spannungseinbruch/Sag)
3. Frequenzstörungen (Frequenzabweichung, Frequenzschwankung)
4. Wellenformstörungen (Oberwellen/Harmonische, Rauschen/Störimpulse)

## 8.

| Störung                  | VFD | VI        | VFI |
| ------------------------ | --- | --------- | --- |
| Stromausfall             | ✅   | ✅         | ✅   |
| Kurzzeitunterbrechung    | ✅   | ✅         | ✅   |
| Unterspannung            | ❌   | ✅         | ✅   |
| Überspannung             | ❌   | ✅         | ✅   |
| Spannungsspitze (Surge)  | ❌   | teilweise | ✅   |
| Spannungseinbruch (Sag)  | ❌   | teilweise | ✅   |
| Frequenzabweichung       | ❌   | ❌         | ✅   |
| Frequenzschwankung       | ❌   | ❌         | ✅   |
| Oberwellen (Harmonische) | ❌   | ❌         | ✅   |
| Rauschen (Störimpulse)   | ❌   | ❌         | ✅   |
> VI/