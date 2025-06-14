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
> **Vertraulichkeit**
>> Hashing
> **Datenintegrität**
>> Verifizierung vollständiger und unveränderter Daten
> **Authentifizierung**
>> Prüfung der Berechtigung
>**Schlüsselmanagement**
>> Regelung der Erzeugung, Verteilung & Erneuerung
> **Sitzungssicherheit**
>> Jede Verbindung neu verschlüsselt mit dynamischen Schlüsseln

9. Gibt es Standards im Bereich WLAN, welche für die Authentifizierung und die Verschlüsselung gleichzeitig verantwortlich sind?
> WPA / WPA2 / WPA3
> **Authentifizierung**
>> WPA/WPA2-Personal (Pre-shared key)
>> WPA/WPA2/WPA3-Enterprize (802.1X + RADIUS)
> **Verschlüsselung**
>> WPA: TKIP
>> WPA2: AES (CCMP)
>> WPA3: AES mit SAE
> IEEE 802.11i
>> Authentifizierung (802.1X, PSK)
>> Verschlüsselung (CCMP/AES)
>> Schlüsselmanagement

10. Was ist der Unterschied zwischen WPA, WPA2 und WPA3?
> **WPA**
>> Erste Verbesserung zu WEP, aber noch unsicher
> **WPA2**
>> Aktueller Standard mit starker AES-Verschlüsselung
> **WPA3**
>> Modern, sicherer, schützt besser vor Passwort-Angriffen und Abhören

11. Erkläre das Verfahren der "Pre shared keys".
> Festgelegtes Passwort, um Nutzer zu Authentifizieren

12. Sie beraten einen Kunden bzgl. des Kaufs eines Accesspoints. Der Kunde fragt sie nach den Sicherheitseinstellungen für sein WLAN. Welche Einstellungen empfehlen sie dem Kunden?
> **Verschlüsselung**  
>> WPA3 verwenden, falls unterstützt; sonst WPA2 (AES/CCMP)  
>> WEP und WPA (TKIP) vermeiden, da unsicher.
> **Authentifizierung**  
>> WPA3-Personal (SAE) oder WPA2-Personal (PSK) für Privatkunden
>> Für Unternehmen WPA2/WPA3-Enterprise mit 802.1X und RADIUS.
> **WPS**  
>> Deaktivieren, da oft unsicher.
> **SSID**  
>> Öffentlich ausstrahlen (Verbergen bringt wenig Sicherheit).
> **Passwort** 
>> Starkes, langes und zufälliges Passwort wählen.
> **Firmware**
>> Regelmäßig Updates des Accesspoints einspielen.
> **Zusätzliche Optionen**  
>> Gäste-WLAN mit eigenem Passwort und isoliertem Netzwerk.  
    MAC-Filterung als ergänzende Maßnahme, aber nicht als Hauptschutz.

