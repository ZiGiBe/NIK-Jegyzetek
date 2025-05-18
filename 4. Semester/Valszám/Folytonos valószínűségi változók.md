# Folytonos valószínűségi változó
- Sűrűségfüggvény: $f = F'(x)$
- Eloszlásfüggvény: $F = \int{f}$
- $R_F$ $\subseteq$ $[0; 1]$ 
- $F$ monoton, növekvő
- $F$ folytonos
- $\lim_{x\to -\infty} F(x) = 0$, illetve $\lim_{x\to \infty} F(x) = 1$
- A valószínűségi változó folytonos, ha az eloszlásfüggvénye abszolút folytonos függvény
- $mod(x)$: A sűrűségfüggvény maximumja
- $med(x)$: Ahol az eloszlásfüggvény értéke $\frac{1}{2}$
	- Ha nincs, akkor ahol átugorja
	- Ha több helyen, akkor $\frac{a+b}{2}$ minden $a$, és $b$ esetén.
- $E(X)$ = $\int^\infty_{-\infty}xf(x)dx$
- $D(X)$ = $E((X- E(X)^2))$
# Egyenletes eloszlás
$$
f(x) = \left\{ \begin{array}{cl}
\frac{1}{b-a}, & \mbox{ha a < x < b};\\
0, &  \mbox{egyébként}.
\end{array} \right.
$$
$$
F(x) = \left\{ \begin{array}{cl}
0, &  \mbox{ha } x \leq a; \\
\frac{x-a}{b-a}, & \mbox{ha } a < x \leq b;\\
1, & \mbox{ha } b < x.
\end{array} \right.
$$
- Jelölés: $\mathcal{U}(a;b)$
- $E(X)$ = $\frac{a+b}{2}$
- $D(X)$ = $\frac{b-a}{\sqrt{12}}$
- Egydimenziós geometriai valószínűségi modell eloszlása
# Exponenciális eloszlás
$$
f(x) = \left\{ \begin{array}{cl}
0, & \mbox{ha x < 0};\\
\lambda e^{-\lambda x}, &  \mbox{x > 0}.
\end{array} \right.
$$
$$
F(x) = \left\{ \begin{array}{cl}
0, &  \mbox{ha } x \leq 0; \\
1- e^{-\lambda x}, & \mbox{ha } x > 0.
\end{array} \right.
$$
- Jelölés: Exp($\lambda$)
- $E(X)$ = $\frac{1}{\lambda}$
- $D(X)$ = $\frac{1}{\lambda}$
- A bekövetkezések átlagos száma egységnyi időintervallumban $\lambda$, akkor a tényleges szám Poisson-eloszlású, a bekövetkezések között eltelt idő pedig exponenciális eloszlású ugyanúgy $\lambda$ paraméterrel.
- Örökifjú, azaz pontosan ugyankkora valószínűséggel kövekezik be $t$ időn belül $s$ eseménytelen várakozás után, mint az elején, tehát:
$$
P(X<s+t|X>s) = P(X<t)
$$
# Normális eloszlás
- X folytonos valószínűségi változót $m$, $\sigma$ ($\sigma$ > 0) paraméterű normális eloszlásnak nevezzük, ha a sűrűség-, és eloszlásfüggvénye a következők:
$$
f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-m)^2}{2\sigma^2}}
$$
$$
F(x) = \frac{1}{\sigma\sqrt{2\pi}} \int^x_{-\infty}e^{-\frac{(t-m)^2}{2\sigma^2}}dt
$$
- $E(X)$ = m
- $D(X)$ = $\sigma$
## Standard normális eloszlás
- Az $m$=0, és $\sigma$=1 szórású normális eloszlást standard normális eloszlásnak nevezzük.
- Jelölés: $\mathcal{N}(m;\sigma)$
- Sztandardizálás: $X^* = \frac{X-E(X)}{D(X)}$
- Szimmetria: $\phi(-x) = 1 - \phi(x)$
- 3$\sigma$ szabály: A várható érték legalább három szórás sugarú környezetén kívül esés valószínűsége a gyakorlatban 0-nak tekinthető
