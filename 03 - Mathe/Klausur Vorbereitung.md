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
# ggT, kgV & Euklidischer Algorithmus
___
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
$$
\begin{flalign}
& 36 \div 2 \rightarrow 18 & & \text{(smallest prime)} && \\
& 18 \div 2 \rightarrow 9 & & \text{" "} && \\
& 9 \div 3 \rightarrow 3 & & \text{" "} && \\
& 3 \div 3 \rightarrow 1 & & \text{" "} && \\
& \text{3 is already a prime (Stop)} &&
\end{flalign}
$$
$36=2^2 \times 3^2$

$$
\begin{flalign}
& 66 \div 2 \rightarrow 33 & & \text{(smallest prime)} && \\
& 33 \div 3 \rightarrow 10 & & \text{" "} && \\
& 10 \div 2 \rightarrow 5 & & \text{" "} && \\
& 5 \div 5 \rightarrow 1 & & \text{" "} && \\
& \text{3 is already a prime (Stop)} &&
\end{flalign}
$$
$36=2^2 \times 3^2$


**kgV**= Kleinstes gemeinsames Vielfaches
