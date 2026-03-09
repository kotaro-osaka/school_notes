# Cascade
## ON DELETE CASCADE
> Wenn in einer Parent table `Besucher` ein Datensatz gelöscht werden soll:
> Wird in der besucht-Tabelle (Child table) der Datensatz zu dem betroffenen Fremdschlüssel ebenfalls gelöscht.

## ON DELETE RESTRICT/NO ACTION
> Datensatz in der Parent table und der Child table wird nicht gelöscht.

## ON UPDATE CASCADE
> Betrifft nur den Schlüssel.
> Das heißt der Fremdschlüssel wird verändert, wenn sich der Primärschlüssel verändert.

## ON UPDATE RESTRICT/NO ACTION
> Der Primärschlüssel ändert sich nicht.
> Der Fremdschlüssel auch nicht.