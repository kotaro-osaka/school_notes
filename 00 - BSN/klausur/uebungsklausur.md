# Übungsklausur
___
## 1.1
Gegeben:
- 4 IP-Kameras
- RJ45
- 10/100 MBit/s

Switch mit 4 Ports (100 MBit/s) wird mit bestehenden Switch in Verkaufshalle verbunden

## 1.2
Gegeben:
- Motion JPEG: 1 Bit/Pixel
- MPEG4: 0,5 Bit/Pixel
- H264: 0,2 Bit/Pixel
- MPEG 2: 0,52 Bit/Pixel

Geringstmögliche Datenmenge => H.264 (0,2 Bit/Pixel)

**Rechnung:**

| Schritt             | Rechnung                               | Ergebnis           |
| ------------------- | -------------------------------------- | ------------------ |
| Pixel pro Bild      | $752 \times 582$                       | $=437.664$ Pixel   |
| Bits pro Bild       | $437.664 \times 0,2 Bit$               | $=87.532,8$ Bit    |
| Bits pro Sekunde    | $87.532,8 \times 25$                   | $=2.188.320$ Bit/s |
| Umrechnung in MiB/s | $2.188.320 \div 8 \div 1024 \div 1024$ | $≈0,261$ MiB/s     |
**≈ 0,261 MiB/s**

## 1.3

| Schritt     | Rechnung         | Ergebnis         |
| ----------- | ---------------- | ---------------- |
| 4 Kameras/s | $0,261 \times 4$ | $=1,044$ MiB/s   |
| Pro Minute  | $\times 60$      | $=62,64$ MiB/min |
| Pro Stunde  | $\times 60$      | $=3.758,4$ MiB/h |
| Pro Tag     | $\times 24$      | $=90.201$        |
