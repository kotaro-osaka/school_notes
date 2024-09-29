# Vektoren
___
> **Darstellung**: $\vec{v}=\begin{pmatrix}v_1 \\ v_2\end{pmatrix}$
## Vektor durch zwei Punkte berechnen
___
![[99 - misc/Pasted image 20240929122203.png|500]]
> “Spitze minus Fuß”
## Skalarmultiplikation
___
> Wird verwendet, um Vektor zu Strecken und Stauchen

$$
\begin{flalign}
	\lambda\times
	
	\begin{pmatrix}
		a_1 \\ a_2
	\end{pmatrix}
	=
	\begin{pmatrix}
		\lambda\times a_1 \\ \lambda\times a_2
	\end{pmatrix} &&
\end{flalign}
$$
> $\lambda=\text{Lambda}$
### Beispiel
$$
\begin{flalign}
	\vec{a} =
	
	\begin{pmatrix}
		3 \\ -2
	\end{pmatrix}
	
	\text{ ; }\lambda=\frac{1}{2}&&
\end{flalign}
$$
$$
\begin{flalign}
	\frac{1}{2} \times
	\begin{pmatrix}
		3 \\ -2
	\end{pmatrix}
	=
	\begin{pmatrix}
		\frac{1}{2} \times 3 \\
		\frac{1}{2} \times (-2)
	\end{pmatrix}
	=
	\begin{pmatrix}
		1,5 \\ -1
	\end{pmatrix}&&
\end{flalign}
$$
## Betrag eines Vektors
___
> **Länge** eines Vektors
> **Darstellung**: $|\vec{v}|=\sqrt{v_1^2+v_2^2}$

![[99 - misc/Pasted image 20240929125235.png|500]]
## Einheitsvektor
___
> Vektoren mit der Länge $1$
> $\vec{e_v}=\frac{1}{|\vec{v}|}\times\vec{v}$
> » “Normieren”

![[99 - misc/videoframe_162647.png|500]]
## Ortsvektor
___
> Zeigt von Ursprung auf gegebenen Punkt

![[99 - misc/Pasted image 20240929182448.png|500]]
> Ausgangspunkt von Endpunkt abziehen
### Schreibweisen
- $\vec{OA}$: Ortsvektor + Punkt
- $\vec{a}$: Punkt
## Winkel zwischen zwei Vektoren
___
1. Skalarprodukt berechnen $\vec{a}\times\vec{b}$
2. Bestimme $\vec{a}\text{ und }\vec{b}$
3. Berechne Formel $$\begin{flalign}cos(\theta)=\frac{\vec{a}\times\vec{b}}{|\vec{a}|\times|\vec{b}|}&&\end{flalign}$$
4. Formel nach $\theta$ umstellen $$\begin{flalign}\theta=cos^{-1}(\frac{\vec{a}\times\vec{b}}{|\vec{a}|\times|\vec{b}|})&&\end{flalign}$$
## Orthogonale Vektoren
___
> Zusammen rechter Winkel
### 2 Vektoren gegeben
1. Skalarprodukt $\vec{a}\times\vec{b}$
2. Wenn $=0$, dann orthogonal
### 1 Vektor gegeben
1. Skalarprodukt $\vec{a}\times\vec{b}$ mit zufälligen Zahlen ($\neq0$) für $b_1$ und $b_2$ nach $b_3$ auflösen
2. Orthogonaler Vektor: $\vec{b}=\begin{pmatrix}b_1 \\ b_2 \\ b_3\end{pmatrix}$
3. 