Egy valószínűségi folytonosnak nevezzünk, eloszlásfüggvénye abszolút folytonos függvény.
$X$ valószínűségi változó eloszlásfüggvényének nevezzük az $F$ függvényt, mely minden valós $x$ értékhez hozzárendeli valószínűségét, hogy $X$ valószínűségi változó $x$-nél kisebb értéket vesz fel.
$$
F(X)=P(X<x); x\in\mathbb{R}
$$
Az $X$ valószínűségi változó folytonos, ha eloszlásfüggvénye integrálfüggvény, azaz $\exists f$ függvény, amelyre igaz, hogy:
$$
\int^x_{-\infty}f(t)dt=F(x); x\in\mathbb{R}
$$
Legyen $X$ valószínűségi változó eloszlásfüggvénye $F(x)$, ha ez abszolút folytonos, akkor $f(x)=F’(x)$, ha egy pontban nem differenciálható, akkor legyen értéke ott 0. Az ezáltal definiált $f(x)$ az $X$ valószínűségi változó sűrűségfüggvénye.
A sűrűségfüggvény tulajdonságai:
- Nem negatív
- $\int^\infty_{-\infty}f(x)dx=1$
**Módusz:** A sűrűségfüggvény ($f(x)$) maximumhelye.
**Medián:** Az a hely ahol az eloszlásfüggvény értéke $\frac{1}{2}$, amint az egyértelmű, amennyiben nem, akkor ahol $\frac{1}{2}$-et átugorja, egyéb esetben, az átugrási pontok átlaga, ahol átugorja ezt az értéket.
**Várható érték:** Legyen $X$ folytonos eloszlású valószínűségi változó, sűrűségfüggvénye $f(x)$. Ekkor $X$ várható értéke $E(X)=\int^\infty_{-\infty}xf(x)dx$ véges integráltat értjük.
**Szórás:** Ha $X$ valószínűségi változónak, és annak négyzetének is létezik, akkor van $X$-nek szórási is, ennek értéke:
$$
D(X)=\sqrt{E(X^2)-E^2(X)}
$$
**Momentum:** $X$ valószínűségi változó $k$. momentumja $X^k$ várható értéke:
$$
m_k=E(X^k)=\sum_i p_ix_i^k=\int_{-\infty}^\infty x^kf(x)dx
$$
