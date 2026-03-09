# Anomalien
___
## Insert-Anomalie
> Ein neuer Datensatz kann nicht gespeichert werden, da andere dafür erforderlichen Daten (noch) nicht existieren.

**Beispiel:**
*Neuer Studiengang wird eingerichtet, aber es gibt noch keine Studenten, die sich für diesen Studiengang eingeschrieben haben.*

**Problem:**
*Einfügen nicht möglich, weil Primärschlüssel MatrikelNr, VeranstalterNr und ProjektID keine Werte erhalten, aber erforderlich sind.*

**Ursache:**
*Mehrere unabhängige Sachverhalte (Entitäten) werden in einer Tabelle gespeichert.*

**Auswirkung:**
- Null-Werte
- Unvollständige Datensätze
## Update-Anomalie
> *Dieselbe Information ist mehrfach in der Tabelle gespeichert (**Redundanz**). Wenn diese Informationen nicht automatisch bei einer Änderung aktualisiert werden, entsteht eine **Inkonsistenz** der Daten.*

**Beispiel:**
*Studiengang wird umbenannt. In Folge dieser Änderung müssen sehr viele Datensätze geändert werden, da dieser Wert redundant gespeichert wird.*

**Problem:**
*Fehlende übergreifende Aktualisierung: **Dateninkonsistenz***

**Ursache:**