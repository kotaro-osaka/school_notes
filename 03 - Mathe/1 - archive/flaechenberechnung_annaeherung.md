# Flächenberechnung Annäherung
> 02.05.2024
___

![[0 - res/flaechenberechnung_annaeherung_skizze.png]]
$A_ \approx =0,5(f(0,5)+0,5 \times f(1)+0,5 \times f(1,5)+0,5 \times ...)$
	$=0,5 \times f(0,5)+f(1)+f(1,5)...$
___

**Breite Rechteck:** $\frac{b-a}{n}$
	**Höhe 1. Rechteck:** $f(a+ \frac{b-a}{n}$
	**Höhe 2. Rechteck:** $f(a+2 \frac{b-a}{n}$
	…
**Höhe n. Rechteck:** $f(a+n \times \frac{b-a}{n})=f(b))$
$$A_ \approx = \frac{b-a}{n} (\sum_{i=1}^nf(a+i \times \frac{b-a}{n}))$$
___

$A_ \approx =\frac{b-a}{n} \times \sum_{i=1}^nf(a+i \frac{b-a}{n})$
**Idee:** Je mehr Rechteck, desto genauer wird die Fläche angenähert
___

**Highlight:** Fundamentalsatz der Integralrechnung
$$\int_a^b f(x)dx=F(b)-F(a)$$
mit $F'f$ Stammfunktion
$f(x)=x^2 \to F(x)= \frac{1}{3} x^3+C$ $\Leftarrow$ Konstante, d.h. die Stammfunktion ist ==nicht== eindeutig
$f(x)=x^3 \to F(x)= \frac{1}{4} x^4+C$
___

$f(x)=- \frac{1}{2} \times x^3+3x+2 \to F(x)- \frac{1}{2} \times \frac{1}{4} x^4+3 \times \frac{1}{2} \times x^2+2x+C$
	$=- \frac{1}{8} x^4+ \frac{3}{2} x^2+2x+C$
$f(x)=3x^3+4x^2+2x-4 \to F(x)= \times{3}{4} x^4+ \frac{4}{3} x^3+x^2-4x+C$
$f(x)=e^{3x}+3x \to F(x)= \frac{1}{3} \times e^{3x} + \frac{3}{2} x^2+C$

**Es gilt:**
$f(x)=x^n \to F(x)= \frac{1}{n+1} x^{n+1}+C$
$f(x)=e^{k \times x} \to F(x)= \frac{1}{e} e^{k \times x}+C$
___

![[0 - res/flaechenberechnung_annaeherung (1).png]]
$a=2, b=5$
$A= \int_2^5 (-x^2+7x \times 10)dx$
$F(x)=- \frac{1}{3} x^3+ \frac{7}{2} \times x^2-10x+C$
$F(5)=-4,1\overline6+C$
$F(2)=8,\overline6 +C$

$\to A= \int_2^5 f( \infty dx=F(5)-F(2)$
	$-4,1 \overline6 +C-(-8, \overline6+C)$
	$4,44[FE]$
