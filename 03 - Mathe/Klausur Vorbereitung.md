# Zahlensysteme & Teiler
___
**Natürliche Zahlen** $\mathbb{N}$: Positive ganze Zahlen, je nach Definition ist 0 miteinbegriffen

**Teilermenge**: Menge aller Teiler einer natürlichen Zahl

**Teilerfremd** $\bot$: Zwei natürliche Zahlen, die keinen gemeinsamen Teiler außer $1$ haben

**Primzahl**: Natürliche Zahl, die durch $1$ und sich selbst teilbar ist
#### Primfaktorzerlegung
Darstellung Zahl $\mathbb{N}$ als Produkt aus Primzahlen $\mathbb{P}$

**Bsp.**
$120$
$$
\begin{flalign}
& 120 \div 2 \rightarrow 60 & & \text{(smallest prime)} && \\
& 60 \div 2 \rightarrow 30 & & \text{" "} && \\
& 30 \div 2 \rightarrow 15 & & \text{" "} && \\
& 15 \div 3 \rightarrow 5 & & \text{" "} && \\
& \text{5 is already a prime (Stop)} &&
\end{flalign}
$$
$120=2^3 \times 3 \times 5$
Primzahlen multiplizieren und Exponenten (Anzahl der Verwendungen) anpassen
# kgV, ggT & Euklidischer Algorithmus
___
**kgV**= Kleinstes gemeinsames Vielfaches (Kleinste Zahl, die ein Vielfaches von Ausgangszahlen ist)

**Bsp.**
$kgV(6, 8)$
$$
\begin{flalign}
& Z_6=\{ 6, 12, 18, 24, 30, ... \} && \\
& 8=\{ 8, 16, 24, 32, ... \} && \\
\end{flalign}
$$
$kgV(6, 8)=24$

#### kgV Primfaktorzerlegung
**Bsp.**
$ggT(54, 63)$
##### 1. Primfaktorzerlegung durchführen
$$
\begin{flalign}
& 54 \div 2 \rightarrow 27 & & \text{(smallest prime)} && \\
& 27 \div 3 \rightarrow 9 & & \text{" "} && \\
& 9 \div 3 \rightarrow 3 & & \text{" "} && \\
& \text{3 is already a prime (Stop)} &&
\end{flalign}
$$
$54=2 \times 3^3$

$$
\begin{flalign}
& 63 \div 3 \rightarrow 21 & & \text{(smallest prime)} && \\
& 21 \div 3 \rightarrow 7 & & \text{" "} && \\
& \text{7 is already a prime (Stop)} &&
\end{flalign}
$$
$63=3^2 \times 7$

##### 2. Einmalig vorkommende Primfaktoren bestimmen
$\rightarrow 2, 7$

##### 3. Höhere Potenz finden
$3^3>3^2 \rightarrow 3^3$

##### 4. Schritt 2 und 3 Zusammenrechnen
$\rightarrow 2 \times 7 \times 3^3=378$
$\rightarrow kgV(54, 63)=378$


**ggT**=Größter gemeinsamer Teiler (Größte Zahl durch die Ausgangszahlen geteilt werden können)

**Bsp.**
$ggT(18, 48)$
$$
\begin{flalign}
& 18=\{ 1, 2, 3, 6, 9, 18 \} && \\
& 48=\{ 1, 2, 3, 4, 6, 8, 12, 16, 24, 48 \} && \\
\end{flalign}
$$
$ggT(18, 48)=6$

#### ggT Primfaktorzerlegung
**Bsp.**
$ggT(36, 66)$
##### 1. Primfaktorzerlegung durchführen
$$
\begin{flalign}
& 36 \div 2 \rightarrow 18 & & \text{(smallest prime)} && \\
& 18 \div 2 \rightarrow 9 & & \text{" "} && \\
& 9 \div 3 \rightarrow 3 & & \text{" "} && \\
& \text{3 is already a prime (Stop)} &&
\end{flalign}
$$
$36=2^2 \times 3^2$

$$
\begin{flalign}
& 66 \div 2 \rightarrow 33 & & \text{(smallest prime)} && \\
& 33 \div 3 \rightarrow 11 & & \text{" "} && \\
& \text{11 is already a prime (Stop)} &&
\end{flalign}
$$
$36=2 \times 3 \times 11$

##### 2. Gemeinsame Primfaktoren bestimmen
$\rightarrow 2, 3$

##### 3. Primfaktoren multiplizieren
$\rightarrow 2 \times 3=6$
$\rightarrow ggT(36, 66)=6$

#### Euklidischer Algorithmus
**Bsp.**
$ggT(12, 27)$

1. Größere durch kleinere Zahl teilen
	$27 \div 12=2$, Rest 3
2. Nenner durch Rest teilen, bis kein Rest übrig bleibt
	$12 \div 3=4$, Rest 0
3. Nenner der letzten Rechnung ist der ggT
	$\rightarrow 3$
	$\rightarrow ggT(12, 27)=3$

#### ggT mit kgV berechnen
$$
\begin{flalign}
	ggT(a, b)=\frac{a \times b}{kgV(a, b)} &&
\end{flalign}
$$

**Bsp.**
$ggT(13, 48)$

##### 1. kgV berechnen
$kgV(13, 48)$

$$
\begin{flalign}
	13 \div 13 \rightarrow 1 &&
\end{flalign}
$$
$13=13 \times 1$

$$
\begin{flalign}
	48 \div 2 \rightarrow 24 && \\
	24 \div 2 \rightarrow 12 && \\
	12 \div 2 \rightarrow 6 && \\
	6 \div 2 \rightarrow 3 && \\
\end{flalign}
$$
$48=2^4 \times 3$

$13 \times 3 \times 2^4=624$

##### 2. ggT bestimmen
$$
\begin{flalign}
	& ggT(13, 48)=\frac{13 \times 48}{624} && \\
	& ggT(13, 48)=\frac{624}{624} && \\
	& \rightarrow ggT(13, 48)=1 &&
\end{flalign}
$$

#### Erweiterter Euklidischer Algorithmus
$a \times x_1 + b \times y_1=ggT(x_1, y_1)$
=> Lösung für $x_1$ und $y_1$ finden

**Bsp.**
$x_1=48$
$y_1=5$
	$\rightarrow ggT=1$
	