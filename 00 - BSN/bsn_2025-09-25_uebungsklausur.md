# Übungsklausur
___
## Aufgabe 1
___
1. *Gilt für die gespeicherten Daten die DSGVO?*
> Ja, da alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, darunter fallen.

2. *Im Datenschutzgesetz steht, dass personenbezogene Daten während der Verarbeitung unversehrt, vollständig und aktuell bleiben müssen. Wie nennt man dieses Schutzziel?*
> Dieses Schutzziel nennt sich Datenintegrität.

3. *Das Unternehmen möchte für Werbezwecke die gespeicherten eMail-Adressen der Kunden an ein anderes Unternehmen weitergeben. Ist das erlaubt?*
> Dies ist nur erlaubt, wenn die betroffene Person dem zustimmt und die Datenübermittlung vertraglich abgesichert ist, damit die dritte Partei die Datenschutzanforderungen einhält.

4. *Zu den Pflichten eines Betreibers von DV-Anlagen, auf dem personenbezogene Daten gespeichert sind gehört die **Speicherkontrolle**. Beschreibe kurz, was man im Rahmen des Datenschutzes unter dieser Pflicht versteht.*
> Die unbefugte Eingabe, Kenntnisnahme, Veränderung oder Löschung ist zu verhindern.

5. *Gebe an, welche technischen Maßnahmen die **Speicherkontrolle** im Netzwerk des Unternehmens KnowIT sicherstellen können.*
> Zugriffsrechte, Rollenverwaltung, Verschlüsselung, Protokollierung, Monitoring, Backups, etc.

## Aufgabe 2
___
3. *Welche Aufgabe hat der Router im geteilten Netzwerk?*
> Der Router leitet Pakete von externen Netzwerken an das Ziel(sub)netz.

4. *Bestimme die Anzahl der IP-Adressen, welche in deinem Netzwerk benötigt werden, damit alle Geräte im Netzwerk entsprechend ihrer Aufgabe kommunizieren können.*
> $10 \text{ PCs} + 1 \text{ Server} + 3 \text{ Routeranschlüsse}=14 \text{ IP-Adressen}$

## Aufgabe 3
___
1. *Warum müssen Subnetze unterschiedliche Netzwerkadressen erhalten?*
> Subnetze müssen unterschiedliche Netzadressen erhalten, weil sie eindeutig voneinander getrennt werden sollen und es sonst zu Adresskonflikten kommen könnte.

2. *Wie viele Subnetze werden insgesamt benötigt? Gebe die neue Subnetzmaske für alle Netzwerke an.*
> Es werden 3 Subnetze benötigt (rot, grün, blau).
> Gegeben: `172.16.192.0/18`
> $2^2=4$ Subnetze  (2 Subnetzbits)
> Neue Subnetzmaske: `255.255.240.0/20`

3. *Lege für alle Subnetze eine Netzwerkadresse fest.*
> 1. `172.16.192.0/20` (`.00`)
> 2. `172.16.208.0/20` (`.01`)
> 3. `172.16.224.0/20` (`.10`)
> 4. `172.16.240.0/20` (`.11`)

4. *Bestimme für jedes Subnetz die Broadcastadresse.*
> 1. `172.16.207.255` (`.00`)
> 2. `172.16.223.255` (`.01`)
> 3. `172.16.239.255` (`.10`)
> 4. `172.16.255.255` (`.11`)

5. *Bestimme die Anzahl möglicher IP-Geräte in jedem Subnetz.*
> $2^{12}-2=4.094$

6. *Gebe den IP-Adressbereich für jedes Subnetz an.*
> 1. `172.16.192.1` - `172.16.207.254`
> 2. `172.16.208.1` - `172.16.223.254`
> 3. `172.16.224.1` – `172.16.239.254`
> 4. `172.16.240.1` – `172.16.255.254`