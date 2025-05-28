## Indikátor változó
Végzünk egy kísérletet egy $p$ valószínűségű $A$ esemény megfigyelésére. $X$ valószínűségi változó értéke legyen 1, ha $A$ bekövetkezik, 0, ha nem. Ekkor $X$ az $A$ esemény indikátor változója, eloszlása pedig:
$$
X: \left\{\begin{array}{cl}
0 && 1 \\
1-p && p
\end{array}\right.
$$
## Egyenletes eloszlás
$X$ valószínűségi változó egyenletes eloszlású, ha $(a;b)$ intervallumon sűrűségfüggvénye:
$$
f(x)=\left\{
\begin{array}{l}
\frac{1}{b-a}\mbox{, ha a < x < b;} \\
0\mbox{, különben.}
\end{array}
\right.
$$
Eloszlásfüggvénye:
$$
F(x)=\left\{
\begin{array}{l}
0\mbox{, ha x < a;} \\
\frac{x-a}{b-a}\mbox{, ha a}\leq x \leq b; \\
1\mbox{, ha b < x.}
\end{array}
\right.
$$
**Várható érték:** $E(X)=\frac{a+b}{2}$
**Szórás:** $D(X)=\frac{b-a}{\sqrt{12}}$
## Exponenciális eloszlás
Egy véletlen esemény egy egységnyi hosszúságú időintervallumban $\lambda$ alkalommal következik be. $X$ valószínűségi változó értéke az esemény két bekövetkezése közötti eltelt idő.
**Sűrűségfüggvény:**
$$
f(x)=\left\{
\begin{array}{ll}
\lambda\cdot e^{-\lambda x}, && \mbox{ha x > 0;} \\
0 && \mbox{különben.}
\end{array}
\right.
$$
**Eloszlásfüggvénye:**
$$
F(x)=\left\{
\begin{array}{ll}
1-e^{-\lambda x}, && \mbox{ha x > 0}; \\
0, && \mbox{ha x} \leq 0.
\end{array}
\right.
$$
**Várható érték:** $E(X)=\frac{1}{\lambda}$
**Szórás**: $D(X)=\frac{1}{\lambda}$

Ha véletlen esemény bekövetkezésének átlagos száma egységnyi időintervallumban $\lambda$, akkor a bekövetkezések tényleges száma Poisson-eloszlású, és a bekövetkezések között eltelt idő pedig exponenciális eloszlású ugyanazzal a $\lambda$ paraméterrel.

**Örökifjú**, azaz $t$ időn belül $s$ ideig való várakozás után ugyan akkora valószínűséggel következik be az esemény, mint az elején, azaz:
$$
P(X<s+t|X>s) = P(X<t)
$$
## Normális eloszlás
$X$ folytonos valószínűségi változót $m$, $\sigma$ paraméterű normális eloszlásúnak nevezzük, ha sűrűségfüggvénye a következő:
$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-m)^2}{2\sigma^2}}
$$
**Eloszlásfüggvénye:**
$$
F(x)=\frac{1}{\sigma\sqrt{2\pi}}\int^x_\infty e^{-\frac{(t-m)^2}{2\sigma^2}}
$$
**Várható érték:** $E(X)=m$
**Szórás:** $D(X)=\sigma$
**3${\sigma}$ szabály:** A gyakorlatban a várható érték három szórás sugarú környezetén kívül esés valószínűsége 0-nak tekinthető.
**Standardizálás:** Tetszőleges, véges várható értékű $X$ valószínűségi változó standardizáltja:
$$
F(x)= \phi  \left( \frac{x-m}{\sigma} \right)
$$