# IPv6 Aufgaben
___
## 1. Erkennung IPv4 vs. IPv6
**Network Layer:**
Host erkennt anhand des **Version-Feldes im IP-Header** (ersten 4 Bits)
- `0100` = `4` → IPv4
- `0110` = `6` → IPv6

**Data-Link Layer:**
**EtherType** im Frame-Header signalisiert verwendete Version
- `0x0800` → IPv4
- `0x86DD` → IPv6

## 2. Adresslänge
- IPv4: 32 Bit
- IPv6: 128 Bit

## 3. ARP-Äquivalent
**IPv4: ARP (Address Resolution Protocol)**
- Löst IP-Adresse in MAC-Adresse auf (Layer 3 → Layer 2)
- Sendet Broadcast-Anfrage um Host mit jeweiligen IP zu finden

**IPv6: NDP (Neighbor Discovery Protocol)**
- Ersetzt *ARP*, *ICMP Router Discovery*, *ICMP Redirect*
- Verwendet **Solicited-Node Multicast-Adressen**, die sich aus `ff02::1:ff` + letzten 24 Bit der Ziel-IPv6-Adresse zusammensetzten
	- **Bsp.:** Wird nach `fe80::a1d6:ffff:acda:16fd` gesucht, wird `ff02::1:ffda:16fd` gesendet
	- **Nur der Host mit der passenden Adresse muss den Frame verarbeiten - alle anderen verwerfen ihn auf Schicht 2**

**ICMPv6-Nachrichtentypen von NDP:**

| Typ | Name                        | Funktion                                                                                                                                                                                                                                                                   |
| --- | --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 133 | Router Solicitation (RS)    | Host sendet diese Nachricht direkt nach dem Verbindungsaufbau ins Netz, um aktiv nach einem Router zu fragen, statt auf das nächste *RA* zu warten                                                                                                                         |
| 134 | Router Advertisement (RA)   | Router senden diese Nachricht alle `200` Sekunden oder als direkte Antwort auf eine *RS*.<br>Enthält `Netzpräfix`, `MTU` des Links, `Gültigkeitsdauer` der Adressen, `Flags`, die dem Host mitteilen, ob `SLAAC` oder `DHCPv6` zur Autokonfiguration verwendet werden soll |
| 135 | Neighbor Solicitation (NS)  | Ersetzt ARP-Request.<br>“Wer hat diese IPv6-Adresse? Antworte mit deiner MAC.”                                                                                                                                                                                             |
| 136 | Neighbor Advertisement (Na) | Ersetzt ARP-Reply.<br>Angesprochene Host antwortet mit seiner MAC-Adresse direkt an den Absender.                                                                                                                                                                          |
| 137 | Redirect                    | Router sendet diese Nachricht an einen Host, wenn er weiß, dass ein anderer Router im selben Subnetz ein besserer nächster Hop für ein bestimmtes Ziel wäre.<br>Host aktualisiert seinen Routing-Cache.<br>Vermeidet unnötige Umwege & entlastet Router.                   |
**Vergleich ARP vs. NDP**

|                 | ARP                                 | NDP                                                                                       |
| --------------- | ----------------------------------- | ----------------------------------------------------------------------------------------- |
| Protokoll       | Eigenständig (EtherType 0x0806)     | Teil von ICMPv6, in IPv6 integriert                                                       |
| Adressierung    | Broadcast - alle müssen verarbeiten | Solicited-Node Multicast - nur betroffene Hosts                                           |
| Netzlast        | Hoch                                | Deutlich geringer                                                                         |
| Sicherheit      | Keine - anfällig für ARP-Spoofing   | Erweiterbar mit `SEND` (Secure NDP)                                                       |
| Funktionsumfang | Nur MAC-Adressauflösung             | Adressauflösung + Router Discovery + SLAAC + DAD (Duplicate Address Detection) + Redirect |
### Weitere NDP-Funktionen:
#### SLAAC - Stateless Address Autoconfiguration
1. Host empfängt Netzpräfix via *RA*
2. Kombiniert Netzpräfix mit Interface-ID
	=> Fertige IPv6-Adresse ohne DHCP
#### DAD - Duplicate Address Detection
- Bevor ein Host eine selbst konfigurierte Adresse nutzt, sendet er eine *NS*-Nachricht an diese *tentative* Adresse
- Antwort = Konflikt => Adresse wird verworfen
#### Router Discovery
- Host finden automatisch ihre Default-Gateway über RS/RA
- Ohne statische Konfiguration oder DHCPv6

## 4. Netz- & Broadcastadresse
Gegeben: `fe80::a1d6:ffff:acda:16fd/80`
Gesucht: Netz- & Broadcastadresse

1. `fe80:0000:0000:0000:a1d6:ffff:acda:16fd` + `/80`
2. Netzanteil: `fe80:0000:0000:0000:a1d6` + `::` => `fe80::a1d6:0:0:0/80`
3. Broadcast: Multicast
4. (Broadcast = “Letzte Adresse”): `fe80::a1d6` + `ffff:ffff:ffff/80` => `fe80::a1d6:ffff:ffff:ffff/80`

## 5. IPv4-mapped IPv6-Adresse
Gegeben: `192.168.5.78`

Wenn IPv4-Hosst über IPv6-Netz kommuniziert, wird automatisch eine **IPv4-mapped IPv6-Adresse** zugewiesen.
**Schema:** `::ffff:<IPv4-Adresse>`

1. `192.168.5.78` → `192`=`C0`, `168`-`A8`, `5`=`05`, `78`=`4E`
2. `::ffff:c0a8:054e`

## 6. Loopback-Adresse
- IPv4: `127.0.0.1`
- IPv6: `::1`

## 7. Kurzform
a) `fe80:00aa:0016:b001:0151:23f3:005a:0613` → `fe80:aa:16:b001:151:23f3:5a:613`
b) `2001:0000:0000:0000:f121:2134:a001:1513` → `2001::f121:2134:a001:1513`
c) `0000:0000:0000:ffff:0192:0168:0001:0152` → `::ffff:192:168:1:152`
d) `fe80:0000:0000:0001:0000:0000:0010:1000` → `fe80::1:0:0:10:1000`

## 8. Vollständige Darstellung von Kurzformen
a) `fe80:127:0:33:5:200:0:1b2c` → `fe80:0127:0000:0033:0005:0200:0000:1b2c`
b) `ff31:1200::2034:1424` → `ff31:1200:0000:0000:0000:0000:2034:1424`
c) `::1` → `0000:0000:0000:0000:0000:0000:0000:0001`
d) `fe::ff:1:2` → `00fe:0000:0000:0000:0000:00ff:0001:0002`
e) `fe80::55:e::169` → Nicht möglich, weil `::` zwei Mal verwendet wurde

## 9. Internetzugriff Problem
`fe80::218:e7ff:fe16:7130/64`

=> Weil es sich um eine Link-Local Adresse handelt, die nicht für routing, sondern für einzelne ‘Links’ verwendet wird.

## 10 Dual Stack
- Übergangstechnologie (entwickelt, um Migration zu erleichtern)
	- Reine IPv4 Geräte können nicht mit reinen IPv6 Geräten kommunizieren
- Dual Stack Geräte betreiben beide Protokolle gleichzeitig auf demselben Interface

| Technologie         | Prinzip                                                                          |
| ------------------- | -------------------------------------------------------------------------------- |
| Dual Stack          | Beide Protokolle laufen gleichzeitig                                             |
| Tunneling           | IPv6-Pakete werden in IPv4-Pakete verpackt und durch ein IPv4-Netz transportiert |
| Translation (NAT64) | Übersetzt IPv6-Pakete in IPv4-Pakete und umgekehrt                               |

## Zusatzaufgabe - Annonymität
**Problem: EUI-64**
- Bei SLAAC generiert ein Host seine Interface-ID ursprünglich nach dem **EUI-64-Verfahren** direkt aus der MAC-Adresse des Netzwerkinterfaces
	=> Resultierende IPv6-Adresse enthält **dauerhaft und weltweit eindeutig** die MAC-Adresse des Geräts
	=> Sichtbar für jeden Router & Server auf dem Weg

**Konsequenzen:**
1. **Geräteidentifikation:** Da die MAC-Adresse herstellerspezifisch ist (ersten 24 Bit), lässt sich nicht nur Gerät, sondern auch dessen Hersteller ablesen
2. **Tracking über Netzgrenzen hinweg:** Nutzer, die sich in verschiedene Netze einloggt, verwenden dieselbe Interface-ID und Dienste können ein Bewegungsprofil erstellen, ohne Cookies oder andere Tracking-Mechanismen zu benötigen

**Reaktion der IETF:**
> ISOC (Internet Society) ist die Dachorganisation der IETF (Internet Engineering Task Force)
- Hat in **RFC 4941** “**Privacy Extensions**” definiert, die inzwischen in allen modernen Betriebssystemen standardmäßig aktiviert sind
	=> Statt aus der MAC-Adresse abzuleiten, wird eine **zufällige, temporäre Interface-ID** generiert, diese wird periodisch erneuert (oft alle 24h)
