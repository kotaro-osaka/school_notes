# Dämpfung
___
$A_u$: Spannungsdämpfungsmaß in $dB$
$U_1$: Eingangsspannung in $V$
$U_2$: Ausgangsspannung in $V$
$A_p$: Leitungsdämpfungsmaß in $dB$

$A_u=20 \times \log \frac{U_1}{U_2}$ $[dB]$ *Pseudoeinheit*
$Ap=10 \times \log \frac{P_1}{P_2}$

## Logarithmus
___
Potenz von Basis herausfinden

$y=10^x$
$log(y)=x$

$1000=10^3$

## Beispiele
___
### 1.
geg.
$U_1=10V$
$U_2=1V$

ges.
$A_u$

$20 \times \log \frac{10V}{1V}$
$=20dB$

$A_u=20dB$

### 2.
geg.
$U_1=100V$
$U_2=1V$

ges.
$Au$

$20 \times \log \frac{100V}{1V}$
$=40dB$

$Au=40dB$

### 3.
geg.
$U_1=1000V$
$U_2=1V$

ges.
$Au$

$20 \times \log \frac{1000V}{1V}$
$=60dB$

$Au=60dB$

### 4.
geg.
$U_1=100000V$
$U_2=1V$

ges.
$Au$

$20 \times \log \frac{1000000V}{1V}$
$=120dB$

$Au=120dB$

___
#### 1.
geg.
$U_1=10V$
$U_2=5V$

ges.
$A_{u1}$

$20 \times \log \frac{10V}{5V}$
$=6dB$

$A_{u1}=6dB$

#### 2.
geg.
$U_3=5V$
$U_4=3V$

ges.
$A_{u2}$

$20 \times \log \frac{5V}{3V}$
$=4,4dB$

$A_u=6dB$

*nach $U_2$ umstellen*
$$
\begin{flalign}
& A_u=20 \times \log \frac{U_1}{U_2} [dB] & & | \div 20 && \\
& \frac{A_u}{20}= \log \frac{U_1}{U_2} & & | \text{ Logarithmus umkehren} && \\
& 10^{ \frac{A_u}{20}}= \frac{U_1}{U_2} & & | \times U_2 && \\
& U_2 \times 10^{ \frac{A_u}{20}}=U_1 & & | \div 10^{ \frac{A_u}{20}} && \\
& U_2= \frac{U_1}{10^{ \frac{A_u}{20}}} &&
\end{flalign}
$$

$U_2=3V$

$A_{u12}$
**ergänzen**

## Aufgaben zu 11.3.2
___
### 1.
**geg.**
$U_1=35mV$
$U_2=11,07mV$

**ges.**
$A_u$

**Rechnung**
$A_u=20 \times \log \frac{0,035V}{0,01107V}$
$=9,99dB$

### 2.
**geg.**
$P_1=1,25mW=0,00125W$
$P_2=85 \micro W=0.000085W$

**ges.**
$A_p$

**Rechnung**
$A_p=10 \times \log \frac{0,00125W}{0.000085W}$
$=11,67dB$

### 3.
**geg.**
$U_1=10V$
$A_u=30dB$

**ges.**
$U_2$

**Rechnung**
$$
\begin{flalign}
& A_u=20 \times \log \frac{U_1}{U_2} [dB] & & | \div 20 && \\
& \frac{A_u}{20}= \log \frac{U_1}{U_2} & & | \text{ Logarithmus umkehren} && \\
& 10^{ \frac{A_u}{20}}= \frac{U_1}{U_2} & & | \times U_2 && \\
& U_2 \times 10^{ \frac{A_u}{20}}=U_1 & & | \div 10^{ \frac{A_u}{20}} && \\
& U_2= \frac{U_1}{10^{ \frac{A_u}{20}}} &&
\end{flalign}
$$

$$
\begin{flalign}
& U_2= \frac{10V}{10^{ \frac{30dB}{20}}} && \\
& U_2=0,316V &&
\end{flalign}
$$

### 4.
**geg.**
$l=760m$
$U_2=0,8mV=0,0008V$
$8dB/100m$

**ges.**
$U_1$

**Rechnung**
$A_u=60,8dB$

$$
\begin{flalign}
& \frac{A_u}{20}= \log \frac{U_1}{U_2} && \\
& \frac{U_1}{U_2}=10^{ \frac{A_u}{20dB}} && \\
& U_1=U_2 \times 10^{ \frac{A_u}{20dB}} &&
\end{flalign}
$$

$$
\begin{flalign}
& U_1=0,0008V \times 10^{ \frac{60,8dB}{20dB}} && \\
& U_1=0,877V &&
\end{flalign}
$$

### 5.
#### a)
**geg.**
$G_u=38dB$
$U_1=2,1mV=0,0021V$

**ges.**
$U_2$

**Rechnung**
$$
\begin{flalign}
& G_u=20 \times \log \frac{U_1}{U_2} [dB] & & | \div 20 && \\
& \frac{G_u}{20}= \log \frac{U_1}{U_2} & & | \text{ Logarithmus umkehren} && \\
& 10^{ \frac{G_u}{20dB}}= \frac{U_1}{U_2} & & | \times U_2 && \\
& U_2 \times 10^{ \frac{G_u}{20dB}}=U_1 & & | \div 10^{ \frac{G_u}{20dB}} && \\
& U_2= \frac{U_1}{10^{ \frac{G_u}{20dB}}} &&
\end{flalign}
$$
$$
\begin{flalign}
& U_2= \frac{U_1}{10^{ \frac{G_u}{20dB}}} && \\
& U_2= \frac{0,0021V}{10^{ \frac{38dB}{20dB}}} && \\
& U_2 \approx 0,0000264V &&
\end{flalign}
$$
#### b)
**geg.**
$U_1=0,0000264V$
$Au=23dB$

**ges.**
$U_2$

**Rechnung**
$$
\begin{flalign}
& A_u=20 \times \log \frac{U_1}{U_2} [dB] & & | \div 20 && \\
& \frac{A_u}{20}= \log \frac{U_1}{U_2} & & | \text{ Logarithmus umkehren} && \\
& 10^{ \frac{A_u}{20dB}}= \frac{U_1}{U_2} & & | \times U_2 && \\
& U_2 \times 10^{ \frac{A_u}{20dB}}=U_1 & & | \div 10^{ \frac{A_u}{20dB}} && \\
& U_2= \frac{U_1}{10^{ \frac{A_u}{20dB}}} &&
\end{flalign}
$$
$$
\begin{flalign}
& U_2= \frac{U_1}{10^{ \frac{Au}{20dB}}} && \\
& U_2= \frac{0,0000264V}{10^{ \frac{23dB}{20dB}}} && \\
& U_2 \approx 0,000001868V
\end{flalign}
$$
### 6.
**geg.**
$P=20W$
$R=7 \ohm$
$U_2=0,058V$
$G=20 \times \log_{10}( \frac{U_1}{U_2})$

**ges.**
$Gu$

**Rechnung**
$U=\sqrt{P \times R}= \sqrt{20W \times 7 \ohm} =11,83V$

$$
\begin{flalign}
& Gu=20 \times \log_{10}( \frac{U_1}{U_2})&& \\
& Gu=20 \times \log_{10}( \frac{11,83V}{0,058V}) && \\
& Gu \approx 46,19dB &&
\end{flalign}
$$
