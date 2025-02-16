# Erweiterter Euklidischer Algorithmus
___
**Formel**:
$a \times x_1+b \times y_1= ggT(x_1, y_1) \rightarrow \text{Lösung für (a, b) finden}$

**Beispiel**:

Geg.:
$x_1=48, y_1=5 \rightarrow ggT(48,5)=1$

Ges.:
$a \times 48+b \times 5=1$

Rechnung:
$a \times 48+b \times 5=1$
$a, b \in \perp$

$$
\begin{flalign}
& 48=9 \times 5+3 & & \rightarrow 3=48-9 \times 5 && \\
& 5=1 \times 3+2 & & \rightarrow 2=5-1 \times 3 && \\
& 3=1 \times 2+1 & & \rightarrow 1=3-1 \times 2 && \\
& 2=2 \times 1 & & =3-1 \times (5-1 \times 3)=2 \times 3-1 \times 5 && \\
& & &  =2 \times (48-9 \times 5)-1 \times 5=2 \times 48-19 \times 5 &&
\end{flalign}
$$