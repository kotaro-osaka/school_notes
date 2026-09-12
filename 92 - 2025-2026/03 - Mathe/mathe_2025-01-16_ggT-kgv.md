# Kryptologie kgV und ggT
___
## kgV
___
## 1.
a) kgV(6; 7) → 42
b) kgV(12; 18) → 36
c) kgV(14; 18) → 126
d) kgV(84; 102) → 1428
### 2.
**a)**
1. kgV(6; 7)
	- $6=2 \times 3$
	- $7=7$
	- kgV: $2 \times 3 \times 7=42$
2. kgV(12; 18)
	- $12=2 \times 2 \times 3$
	- $18=2 \times 3 \times 3$
	- kgV: $2 \times 2 \times 3 \times 3=36$
3. kgV(14; 18)
	- $14=2 \times 7$
	- $18=2 \times 3 \times 3$
	- kgV: $2 \times 3 \times 3 \times 7=126$
4. kgV(84; 102)
	- $84=2 \times 2 \times 3 \times 7$
	- $102=2 \times 3 \times 17$
	- kgV: $2 \times 2 \times 3 \times 7 \times 17=1428$
**Regel**
- Primfaktorzerlegungen der beiden Zahlen bestimmen
- Für jeden Primfaktor die **höchste Potenz**, die in einer der beiden Zerlegungen vorkommt bestimmen
- Gewählte Potenzen multiplizieren, um **kgV** zu bestimmen

**b) Überprüfung der Regel**
1. kgV(20; 30)
	- $20=2 \times 2 \times 5,30=2 \times 3 \times 5$
	- Höchste Potenzen: $2 \times 2 \times 3 \times 5=60$
	- $kgV(20, 30)=60$
2. kgV(9; 15)
	- $9=3 \times 3,15=3 \times 5$
	- Höchste Potenzen: $3 \times 3 \times 5=45$
	- $kgV(9, 15)=45$

c) kgV(9000; 41580)
1. Zerlegungen
	- $9000=2 \times 2 \times 2 \times 3 \times 3 \times 5 \times 5 \times 5$
	- $41580=2 \times 2 \times 3 \times 3 \times 3 \times 5 \times 7 \times 11$
2. Höchste Potenzen
	- $2^2$ (beide Zahlen)
	- $3^3$ ($41580$)
	- $5^3$ (9000)
	- $7^1$ ($41580$)
	- $11^1$ ($41580$)
3. Berechnung
	$kgV(9000, 41580)=2^3 \times 3^3 \times 5^3 \times 7 \times 11=124740000$
### 3.
**geg.**
- Anzahl d. Umdrehungen des kleinen Zahlenrads: $x$
- Anzahl d. Umdrehungen des großen Zahlenrads: $y$

**ges.**
$kgV(x, y)$
> *Das $kgV(x, y)$ gibt die Anzahl der Umdrehungen des kleinen Zahlenrads an, die auch die Umdrehungen des großen Zahlenrads synchronisieren.*

**Rechnung**
1. Umdrehungen bestimmen
2. Primfaktorzerlegung beider Zahlen bestimmen
3. $kgV(x, y)$ berechnen

**Beispiel**
1. 
	- $x=5$
	- $y=8$
2. 
	- $5=5$ (Primzahl)
	- $8=2 \times 2 \times 2=2^3$
3. 
	- $kgV(5, 8)=2^3 \times 5=40$
Ergebnis: $40$
### 4.
> Das kgV der Nenner zweier Brüche kann verwendet werden, um Brüche schneller auf denselben Nenner zu bringen.

**Beispiel Addition** von $\frac{3}{4} + \frac{5}{6}$
1. Nenner: 4, 6
2. $kgV(4, 6)=12$
3. 
	- $\frac{3}{4} = \frac{9}{12}$ (Zähler mit $12 \div 4=3$ multiplizieren)
	- $\frac{5}{6} = \frac{10}{12}$ (Zähler mit $12 \div 6=2$ multiplizieren)
4. $\frac{9}{12} + \frac{10}{12} = \frac{19}{12}$

**Beispiel Subtraktion** von $\frac{7}{8} - \frac{1}{5}$
1. Nenner: 8, 5
2. $kgV(8, 5)=40$
3. 
	- $\frac{7}{8} = \frac{35}{40}$ (Zähler mit $40 \div 8=5$ multiplizieren)
	- $\frac{1}{5} = \frac{8}{40}$ (Zähler mit $40 \div 5=8$ multiplizieren)
4. $\frac{35}{40} - \frac{8}{40} = \frac{27}{40}$

**Vergleich mit und ohne kgV**
- **Mit kgV:** Effizienter, da gemeinsamer Nenner direkt minimiert wird
- **Ohne kgV:** Mehr Arbeit, da Nenner größer ist und Ergebnis oft gekürzt werden muss
## ggT
___
### 1.
a) ggT(12; 18) → 6
b) ggT(15; 45) → 15
c) ggT(64; 96) → 32
d) ggT(65; 91) → 13
### 2.
**a)**
1. ggT(12; 18)
	- $12=2 \times 2 \times 3$
	- $18=2 \times 3 \times 3$
	- $ggT(12, 18)=2 \times 3=6$
2. ggT(15; 45)
	- $15=3 \times 5$
	- $45=3 \times 3 \times 5$
	- $ggT(15, 45)=3 \times 5=15$
3. ggT(64, 96)
	- $64=2 \times 2 \times 2 \times 2 \times 2 \times 2=2^6$
	- $96=2 \times 2 \times 2 \times 2 \times 2 \times 3=2^5 \times 3$
	- $ggT(64, 96)=2^5=32$
4. ggT(65; 91)
	- $65=5 \times 13$
	- $91=7 \times 13$
	- $ggT(65, 91)=13$
**Regel**
- Primfaktoren beider Zahlen bestimmen
- Gleiche Primfaktoren bestimmen
- Primfaktoren, die in beiden Zerlegungen vorkommen mit jeweils kleineren Potenz multiplizieren

**b)**
https://chatgpt.com/c/67875a02-8bf8-8004-848b-f5b24ed90c49