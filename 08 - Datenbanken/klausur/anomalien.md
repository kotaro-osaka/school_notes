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
*Datenredundanz*

**Auswirkung:**
- Dateninkonsistenz
- Hoher Wartungsaufwand

## Delete-Anomalie
> Beim Löschen von Werten eines Datensatzes werden andere Daten mitgelöscht, obwohl die weiterhin benötigt werden.

**Beispiel:**
*Ein Student verlässt die Uni. Dabei wird der Studiengang, Dozent, etc. mitgelöscht.*

**Problem:**
*Daten, die erhalten bleiben sollen, werden gelöscht.*

**Ursache:**
*Unabhängige Entitäten befinden sich in einer Tabelle.*

**Auswirkungen:**
- Informationsverlust
- Ungewolltes