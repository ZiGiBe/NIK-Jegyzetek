## Hipergeometriai eloszlás közelítése binomiális eloszlással
Legyen $p$ egy 0 és 1 közé eső szám, illetve $s_m$ olyan egész értékű sorozat, amely:
$$
\lim_{m\to\infty}\frac{s_m}{m}=p
$$
Legyen $n$ olyan $m$-től és $s_m$-től független egész állandó, melyre igaz, hogy $n\leq s_m$ és $n\leq m-s_m$. Ekkor tetszőleges $k$ esetén:
$$
\lim_{m\to\infty}\frac{{s_m\choose k}\cdot{m-s_m \choose n-k}}{m \choose n} = {n \choose k} \cdot p^k\cdot (1-p)^{n-k}
$$
## Binomiális eloszlás közelítése Poisson-eloszlással
Legyen $\lambda$ egy pozitív szám, és $p_n$ 0 és 1 közötti számok olyan sorozata, amelynél:
$$
\lim_{n\to \infty}p_n\cdot n = \lambda
$$
Ekkor tetszőleges $k$ esetén:
$$
\lim_{n\to\infty}{n \choose k} \cdot p^k_n\cdot(1-p_n)^{n-k}=\frac{\lambda^{k}}{k!}\cdot e^{-\lambda}
$$
## Határeloszlás tételek
### de Moivre-Laplace-tétel
Legyen $X$ binomiális eloszlású valószínűségi változó $n$, $p$ paraméterekkel. Ekkor a várható valószínűségi változó várható értéke $n\cdot p$, szórása $\sqrt{np(1-p)}$. 
1. Ilyenkor megfelelően nagy ($n>30$) esetén annak valószínűsége, hogy $X$ pontosan $k$ közelíthető egy azonos várható értékkel, szórással bíró normális eloszlás sűrűségfüggvényének segítségével (lokális alak).
2. Ilyenkor annak a valószínűsége, hogy $X$ értéke $a$, és $b$ közé esik, megbecsülhető egy azonos várható értékkel és szórással bíró normális eloszlás eloszlásfüggvényének segítségével (globális alak).
$X$ binomiális eloszlású valószínűségi változó $n, p$ paraméterekkel amennyiben elég nagy $n$ értékkel rendelkezik, akkor annak valószínűsége, hogy $X$ $a, b$ számok által határolt intervallumba esik, az becsülhető a normális eloszlás eloszlásfüggvényével, azaz:
$$
P(a\leq X\leq b) \approx \phi\left(\frac{b+0.5-np}{\sqrt{np(1-p)}}\right)-\phi\left(\frac{a-0.5-np}{\sqrt{np(1-p)}}\right)
$$
### Központi határeloszlás tétel
Legyenek $X_1, X_2, \dots, X_n, \dots$ független, azonos eloszlású valószínűségi változók létező, azonos várható értékkel és szórással. Ekkor $X_i$ valószínűségi változók összegének standardizáltja határesetben standard normális eloszlású, tehát:
$$
lim_{n\to\infty}P\left(\frac{X_1+X_2+\dots{}+X_n-n\cdot m}{\sigma\sqrt{n}} < x \right) = \frac{1}{\sqrt{2\pi}}\int^x_{-\infty}e^{\frac{-t^2}{2}}dt=\phi(x)
$$