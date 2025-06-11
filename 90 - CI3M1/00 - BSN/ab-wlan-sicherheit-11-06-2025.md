# WLAN Sicherheit
___
1. Wie erkennt ein potenzieller Angreifer die Existenz eines Funknetzes?
> Das Funknetz strahlt seine SSID in Form eines Beacons aus.

2. Wie kommt ein potenzieller Angreifer an die benötigten Informationen eines Funknetzes, um dieses einzudringen?
> Brute-force
> Phishing / Social Engineering
> Sniffing (3rd party fängt unverschlüsselten Datenverkehr ab)

3. Was versteht man unter einem "closed wired system"?
> Ein System, das nicht mit öffentlichen Netzwerken verbunden ist

4. Wie kann man unbekannten Hosts den Zugang zu einem WLAN sperren und wie kann dieser Schutz umgangen werden?
> WPA2- / WPA3-Verschlüsselung mit Passwort
>> Evil Twin (Rogue AP)
> MAC filter (Whitelist)
>> Mac spoofing (Übernahme von MAC eines Geräts)
> SSID verstecken
> VLAN Isolation

5. Ein Benutzer konfiguriert den Zugang seines WLANs mit der Einstellung WEP. Welche der folgenden Sicherheitsaspekte wird mit WEP eingestellt?
> Vertraulichkeit der Daten
> "Wired equivalent privacy"
> Veraltete und unsichere art der Verschlüsselung
> RC4: Verschlüsselungsverfahren

6. Im WLAN-Standard wird nach Authentisierungsmethode und Verschlüsselungsmethode unterschieden. Welche der folgenden Begriffe beziehen sich auf die Authentisierung, welche auf die Verschlüsselung?
> IEEE 802.1x (Authentisierung) - Zugangsprotokoll
> TKIP (Verschlüsselung) - WPA
> AES (Verschlüsselung) - "Advanced Encryption Standard"; WPA2 & WPA3
> MICHAEL (Verschlüsselung) - "Message Integrity Code Hashed Message Authentication Code"
> EAP (Authentisierung) - "Extensible Authentication Protocol"

7. Welche Aufgabe hat ein RADIUS-Server in einem lokalen Netzwerk?
> "Remote Authentication Dial-In User Service"
> Netzwerkdienst zur **Authentifizierung**, **Autorisierung** und **Abrechnung** (AAA)

8. Nenne Eigenschaften von Verschlüsselungsverfahren im WLAN-Umfeld.
> **Vertraulichkeit** (Hashing)
> **Datenintegrität** (Verifizierung vollständiger und unveränderter Daten)
> **Authentifizierung** ()