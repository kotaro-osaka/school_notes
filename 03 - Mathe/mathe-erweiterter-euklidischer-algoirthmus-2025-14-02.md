# Erweiterter Euklidischer Algorithmus
___
**Formel**:
$a \times x_1+b \times y_1= ggT(x_1, y_1) \rightarrow \text{Lösung für (a, b) finden}$

**Beispiele**:

1.
Geg.:
$ggT(150, 12)$

Rechnung
$$
\begin{flalign}
& 150=12 \times 12+6 && \\
& 12=1 \times 6+6 && \\
& 6=1 \times 6+0 &&
\end{flalign}
$$
$\rightarrow ggT(150, 12)=6$

Erweiterter eukl. ALgorithmus:
$a \times 150+b \times 12=6$

$$
\begin{flalign}
& 150=12 \times 12+6 & & \rightarrow 6=150-12 \times 12 && \\
& 12=1 \times 6+6 & & \rightarrow 6=12-1 \times 6 && \\
& & & = 12-1 \times (12-1 \times 6)= 
\end{flalign}
$$

$$
\begin{flalign}
& 150 = 12 \times 12 + 6 & & \rightarrow 6 = 150 - 12 \times 12 && \\
& 12 = 2 \times 6 + 0 & & \text{(Abbruch, da Rest 0)} && \\
& & & = 150 - 12 \times 12 &&
\end{flalign}
$$


$$\begin{flalign}
& 152 = 12 \times 12 + 8 & & \rightarrow 8 = 152 - 12 \times 12 && \\ & 12 = 1 \times 8 + 4 & & \rightarrow 4 = 12 - 1 \times 8 && \\
& 8 = 2 \times 4 + 0 & & \text{(Abbruch, da Rest 0)} && \\
& & & = 12 - 1 \times (152 - 12 \times 12) && \\
& & & = 12 - 1 \times 152 + 12 \times 12 && \\
& & & = 12 \times 13 - 152 \times 1 &&
\end{flalign}$$