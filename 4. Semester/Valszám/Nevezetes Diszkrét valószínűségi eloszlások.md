## Geometriai eloszlás
Független kísérleteket végzünk egy $p$ valószínűségű eseményre. $X$ valószínűségi változó értéke az első bekövetkezésig szükséges kísérletek száma. Az ilyen eloszlást **geometriai eloszlásnak** nevezzük.
$$
P(X=k) = (1-p)^{k-1} p, \mbox{ahol k} \in \{1;2;3;\dots\}
$$
- Várható érték: $E(X)=\frac{1}{p}$
- Szórás: $D(X)=\sqrt{\frac{1-p}{p^2}}$
- Jelölés: $X \sim \text{Geo}(p)$
- Örökifjú, azaz: $P(X=k + l | X > l) = P(X=k)$
## Binomiális eloszlás
$p$ valószínűségű eseményre $n$ független kísérletet végzünk. $X$ valószínűségi változó értéke a sikeres kísérletek száma, ilyenkor az eloszlást **binomiális eloszlásúnak** nevezzük.
$$
P(X=k) = {n\choose k}
$$
- Várható érték: $E(X) = np$
- Szórás: $D(X)=\sqrt{np(1-p)}$
- Jelölés: $X \sim \mathcal{B}(n;p) \sim \text{Binom}(n;p)$
## Hipergeometriai eloszlás
$N$ elemű sokaságban $s$ kitüntetett. Ennek aránya a sokaságban $p=\frac{s}{N}$ A sokaságból kiveszünk $n$ elemet. $X$ valószínűségi változó értéke a mintában kitüntetett elemek száma, ezt **hipergeometriai eloszlásnak** nevezzük.
$$
P(X=k)=\frac{{s \choose k}{N-s\choose n-k}}{{N \choose n}}
$$
- Várható érték: $E(X) = n\frac{s}{N}=np$
- Szórás: $D(X)=\sqrt{np(1-p)(1-{n-1\choose N-1})}$
- Jelölés: $X \sim \text{HGeo}(n;N;s)$
## Poisson-eloszlás
Egy véletlen esemény rögzített hosszúságú időközönként átlagosan $\lambda$-szor következik be. $X$ valószínűségi változó ennek tényleges bekövetkezéseinek száma adott időintervallumban. Ezt **Poisson-eloszlásnak** nevezzük.
$$
P(X=k)=e^{-\lambda}\cdot\frac{\lambda^k}{k!}, \mbox{ahol k}\in\{0;1;2;\dots\}
$$
- Várható érték: $E(X)=\lambda$
- Szórás: $D(X)=\sqrt{\lambda}$
- Jelölés: $X \sim \text{Poisson}(\lambda)$
