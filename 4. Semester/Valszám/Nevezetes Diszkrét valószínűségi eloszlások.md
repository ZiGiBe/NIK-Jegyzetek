## Indikátor változó
Végezzünk el egy kísérletet $p$ valószínűségű $A$ esemény megfigyelésére, $X$ valószínűségi változó értéke legyen 1, ha $A$ bekövetkezik, viszont 0, ha nem. Ekkor $X$ az $A$ esemény indikátor változója, eloszlása pedig:
$$
X: \left\{ 

\begin{array}{cl}
0 && 1 \\
1-p && p
\end{array}

\right.
$$
## Geometriai eloszlás
$p$ valószínűségű $A$ eseményre addig végzünk független kísérleteket, amíg nem következik be. A szükséges kísérletek száma legyen $X$, ekkor $X$ geometriai eloszlású $p$ paraméterrel.
$$
P(X=k)=(1-p)^{k-1}\cdot p
$$
Jelölése: $\mbox{Geo(p)}$
**Várható érték:** $E(X)=\frac{1}{p}$
**Szórás:** $D(X)=\sqrt{\frac{1-p}{p^2}}$
A geometriai eloszlás **örökifjú**, tehát $z$. próba után $m$. próba bekövetkezése pontosan ugyan akkora valószínűségű, azaz:
$$
P(X=z+m|X>z)=P(X=m)
$$
## Binomiális eloszlás
$n$ darab független kísérletet elvégzünk egy $p$ valószínűségű $A$ esemény megfigyelésére. $X$ valószínűségi változó értéke pedig a sikeres kísérletek száma ($0,1,2,\dots,n$), ekkor $X$ binomiális eloszlású valószínűségi változó $n$, és $p$ paraméterekkel.
Jelölés: $\mbox{Binom}(n;p)$
$$
P(X=k)= {n \choose k}p^k(1-p)^{n-k}
$$
**Várható érték**: $E(X)=np$
**Szórás**: $\sqrt{np(1-p)}$
## Hipergeometriai eloszlás
$m$ darab elemből $s$ elemet megkülönböztetünk. $m$ elemből $n$ darabot kiválasztunk visszatétel nélkül. $X$ a valószínűségi változó értéke $n$ darab kiválasztott megkülönböztetett elemek száma. Ekkor $X$ hipergeometriai eloszlású $m$, $n$ paraméterekkel.
$$
P(X=k)=\frac{{s \choose k}\cdot {m-s\choose n-k}}{{m \choose n}}
$$
Jelölés: $\mbox{HGeo}(n;m;s)$
**Várható érték:** $E(X)=n\cdot \frac{s}{m} = n\cdot p$
**Szórás:** $D(X)=\sqrt{np(1-p)(1-\frac{n-1}{m-1})}$
## Poisson-eloszlás
Véletlen esemény rögzített időintervallumban átlagosan $\lambda$ alkalommal következik be. $X$ valószínűségi változó értéke a tényleges bekövetkezéseinek száma az intervallumban, ilyenkor $X$ valószínűségi váltózót Poisson-eloszlásúnak nevezzük.
$$
P(X=k)=e^{-\lambda}\cdot \frac{\lambda^k}{k!}
$$
Jelölése: Poisson($\lambda$)
**Várható érték:** $E(X)=\lambda$
**Szórás:** $D(X)=\sqrt{\lambda}$