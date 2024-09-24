# Datenbanken
___
## Aufbau & Organisation
**Datenunabhängigkeit**:
> - Trennung von ==physischer Speicherung== von Daten und deren ==Verwaltung== von ==Anwendungsprogrammen==
> - Unterscheidung zwischen logischer ==Gesamtstruktur== und ==anwenderspezifischer== Sicht auf Daten 
> 
>> **Physische Datenunabhängigkeit**:
>> - ==Transparente Organisation== von Daten für Programme und Nutzer 
>> - ==Strukturanpassung== ist unabhängig von Programmen
>
>> **Sicht**:
>> - Ausschnitt einer Datenbank
>> - Enthält anwendungsrelevante Daten

## 3-Ebenen-Modell
- Dient zur Verdeutlichung des Prinzips der physischen und logischen Datenunabhängigkeit
![[Pasted image 20240129115744.png|500]]
![[Pasted image 20240129115955.png|500]]
**Externe Ebene**:
> Darstellung der Daten in Anwendungsanforderung-erfüllender Form (Sichten)

**Konzeptionelle Ebene**:
> Zusammenfassung der Daten eines Anwendungsbereichs, die in einer Datenbank gespeichert werden sollen

**Interne Ebene**:
> Organisation der Daten auf Speichermedien und deren Zugriffsmöglichkeiten

