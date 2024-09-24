# IPv6
___
- 128Bit
- [RFC 4291 Regulation](https://datatracker.ietf.org/doc/html/rfc4291)
## Ohne Subnetting-Berücksichtigung
> Default: `/64`-Prefix
![[Pasted image 20240408095946.png|500]]
> 2 IPv6-Adressteile
## Mit Subnetting-Berücksichtigung
![[Pasted image 20240408100129.png|500]]
> 3 IPv6-Adressteile
> 48, 16, 64
## -Routing-Präfix
- Anzahl der Netzbits
### Global-Routing-Präfix
> Mit Subnetting-Berücksichtigung
> "Netzwerkpräfix" // "Standortpräfix"
- Präfix: `<64`
- Angabe des Lokalen (Sub-)Netzes (Adressbereich)
#### Beispiel
`2001:820:9511:0000::`-`2001:0820:9511:FFFF:FFFF:FFFF:FFFF:FFFF`
> `2001:820:9511::/48`
## Interface ID
___
### Privacy Extensions
- Automatische zufällige Generierung vom Host
- Temporär
- Generated in addition to static / SLAAC-assigned address
- Change periodically
### MAC-Adresse-Basiert
1. Splitting: `48-bit` MAC-Adresse in 2 `24-bit` Hälften teilen
2. `FF`: `FE` zwischen beiden `24-bit`-Hälften einfügen (`=64-bit`)
3. Siebtes Bit: 7. Bit der Interface ID invertieren

![[mac_address_to_link_local.png]]