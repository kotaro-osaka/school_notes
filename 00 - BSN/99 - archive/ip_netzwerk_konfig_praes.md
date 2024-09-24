# 1
1. **IP-Adresse**: Dies ist die eindeutige Adresse, die der Client im Netzwerk verwendet. Sie ermöglicht die Kommunikation mit anderen Geräten im Netzwerk.
2. **Subnetzmaske**: Diese bestimmt, welche Teile der IP-Adresse das Netzwerk und welche Teile den Host identifizieren. Sie wird verwendet, um das Netzwerksegment zu bestimmen, zu dem ein Gerät gehört.
3. **Gateway-Adresse (Standardgateway)**: Dies ist die IP-Adresse des Routers, der den Datenverkehr zwischen dem lokalen Netzwerk und anderen Netzwerken (z.B. dem Internet) vermittelt. Sie wird verwendet, um Datenpakete außerhalb des lokalen Netzwerks zu senden.
4. **DNS-Server-Adresse**: Dies ist die Adresse des Servers, der Domainnamen in IP-Adressen umwandelt. Sie wird verwendet, um menschenlesbare Domainnamen in die entsprechenden IP-Adressen umzuwandeln, die für die Netzwerkkommunikation benötigt werden.
# 2
Die Fritzbox hat standardmäßig eine automatische DHCP-Konfiguration aktiviert. Die Standard-IP-Adresse für das Fritzbox-Gerät ist in der Regel 192.168.178.1, und es vergibt IP-Adressen im Bereich von 192.168.178.20 bis 192.168.178.200 an die Geräte im Netzwerk.

Um die Vorgabe bzgl. der Netzadresse mit “10.100.100.0/24” zu erfüllen, müssen Sie die folgenden Änderungen in der Fritzbox vornehmen:

1. Melden Sie sich an der Benutzeroberfläche der Fritzbox an.
2. Gehen Sie zu “Heimnetz” -> “Netzwerk” -> “Netzwerkeinstellungen”.
3. Klicken Sie auf “IPv4-Adressen”.
4. Ändern Sie die “IPv4-Adresse” der Fritzbox auf “10.100.100.1”.
5. Ändern Sie den “IPv4-Adressbereich für die DHCP-Serverzuweisung” auf “10.100.100.20” bis “10.100.100.200”.
6. Klicken Sie auf “OK”, um die Änderungen zu speichern.

Bitte beachten Sie, dass die genauen Schritte je nach Modell und Firmware-Version der Fritzbox variieren können. Es ist immer ratsam, die Bedienungsanleitung Ihres speziellen Fritzbox-Modells zu konsultieren.
# 3
Der DHCP-Client-Server-Mechanismus besteht aus vier Schritten, die als DORA-Prozess bekannt sind:

1. **Discovery**: Der DHCP-Client sendet eine DHCPDISCOVER-Nachricht, um einen DHCP-Server im Netzwerk zu finden. Dies ist eine Broadcast-Nachricht, die an alle Geräte im Netzwerk gesendet wird.
    
2. **Offer**: Wenn ein DHCP-Server die DHCPDISCOVER-Nachricht erhält, antwortet er mit einer DHCPOFFER-Nachricht, die eine IP-Adresse für den Client enthält.
    
3. **Request**: Nachdem der DHCP-Client die DHCPOFFER-Nachricht erhalten hat, sendet er eine DHCPREQUEST-Nachricht an den DHCP-Server, um die angebotene IP-Adresse anzufordern.
    
4. **Acknowledgement**: Der DHCP-Server sendet eine DHCPACK-Nachricht an den Client, um zu bestätigen, dass die IP-Adresse erfolgreich zugewiesen wurde.
    

Dieser Prozess ermöglicht es dem DHCP-Client, automatisch eine IP-Adresse und andere Netzwerkinformationen vom DHCP-Server zu erhalten. Es ist wichtig zu beachten, dass dieser Prozess jedes Mal durchgeführt wird, wenn ein Gerät eine Verbindung zum Netzwerk herstellt.
# 4
Die Netzadresse “10.100.100.0/24” bedeutet, dass die ersten 24 Bits der IP-Adresse das Netzwerk identifizieren und die restlichen 8 Bits die Hosts innerhalb des Netzwerks. Um die Subnetzmaske in gepunktet dezimaler Form zu erhalten, müssen wir die 24 Einsen in die ersten drei Oktette und die 8 Nullen in das letzte Oktett umwandeln. Das ergibt:

11111111.11111111.11111111.00000000

oder

255.255.255.0

in gepunktet dezimaler Form. Das ist die Subnetzmaske, die Sie für den DHCP-Server konfigurieren müssen.

Die zusätzliche Funktionalität, die auf der Fritzbox in seiner Funktion als Router zwingend aktiviert sein muss, ist **NAT** (Network Address Translation). NAT ermöglicht es, dass mehrere Geräte im lokalen Netzwerk die gleiche öffentliche IP-Adresse verwenden, um mit dem Internet oder anderen externen IP-Netzen zu kommunizieren. Ohne NAT würde jedes Gerät im lokalen Netzwerk eine eigene öffentliche IP-Adresse benötigen, was knapp und teuer wäre. [NAT erhöht auch die Sicherheit, indem es verhindert, dass externe Geräte direkt auf die lokalen Geräte zugreifen können](https://www.livewatch.de/de/tools/subnetz/rechner) [1](https://www.livewatch.de/de/tools/subnetz/rechner)[2](https://bing.com/search?q=Fritzbox+Router+Funktionen).

VPN (Virtual Private Network) ist eine Funktion, die es ermöglicht, eine sichere Verbindung zu einem anderen Netzwerk über das Internet herzustellen. VLAN (Virtual Local Area Network) ist eine Funktion, die es ermöglicht, ein physisches Netzwerk in mehrere logische Netzwerke zu unterteilen. DNS (Domain Name System) ist eine Funktion, die es ermöglicht, Domainnamen wie www.bing.com in IP-Adressen wie 204.79.197.200 aufzulösen. [Diese Funktionen sind nicht zwingend erforderlich, um die Kommunikation in das Internet oder andere externe IP-Netze zu ermöglichen, sondern bieten zusätzliche Vorteile wie Sicherheit, Flexibilität und Benutzerfreundlichkeit](https://www.livewatch.de/de/tools/subnetz/rechner) [1](https://www.livewatch.de/de/tools/subnetz/rechner)[2](https://bing.com/search?q=Fritzbox+Router+Funktionen).
# 5
