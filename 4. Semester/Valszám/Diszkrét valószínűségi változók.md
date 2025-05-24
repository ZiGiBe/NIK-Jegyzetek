A diszkrét valószínűségi változót meg lehet adni / ábrázolni:
- Felsorolással
- Táblázattal
- Grafikonnal
- Képlettel
## Valószínűségi függvény
Valószínűségi függvénynek nevezzük a diszkrét valószínűségi változóban a $f: \mathbb{R}\rightarrow\mathbb{R}, f(x)=P(X=x)$ függvényt.
### Tulajdonságok
- $R_f \subseteq \mathbb{R}^+_0$
- $\sum_{x\in R_x}f(x) = 1$
## Eloszlásfüggvény
$X$ valószínűségi változó eloszlásfüggvénye $F: \mathbb{R} \rightarrow \mathbb{R}, F(x) = P(X<x)$ 
### Tulajdonságok
- $D_F = \mathbb{R}$
- $R_F \subseteq [0;1]$
- Monoton növekvő
- Balról minden pontban folytonos
- $\lim_{x\to -\infty}F(x)=0$
- $\lim_x\to\infty F(X)=1$
## Középértékek
- **Módusz**: Az a $x_i$ hely, melyre $p_i$ maximális, jele: $\text{mod}(X)$
- **Medián**: Az az $x$ érték, ahol $P(X \leq x)$ és $P(X\geq x)$ legalább $\frac{1}{2}$. Jele: $\text{med}(X$)
## Mérőszámok
- Várható érték: $E(X)=\sum_i p_ix_i = \sum_{x\in R_x}xf(x)$
- Szórás: $D^2(X) = E(X^2) - E(X)^2$