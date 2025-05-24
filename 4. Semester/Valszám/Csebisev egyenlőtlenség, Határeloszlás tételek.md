# Csebisev-egyenlőtlenség
$$
P(|X-E(X)| \geq kD(X)) \leq \frac{1}{k^2}
$$
$$
P(|X-E(X)|< kD(X)) > 1 - \frac{1}{k^2} 
$$
# Centrális határeloszlás tétele
- Legyenek $X_1, X_2, \dots, X_n, \dots$ független, azonos eloszlású valószínűségi változók, létező és azonos E(X)-el, és D(X)-el. Ekkor az $X_i$ valószínűségi változó összegének standardizáltja határesetben standard normális értékű.
# de Moivre-Laplace tétel
## Lokális alakra
- Legyen $X$ binomiális eloszlású valószínűségi változó $n$, $p$ paraméterekkel. Ekkor elég nagy $n$ 
  ($n$>30) esetén, akkor annak valószínűsége, hogy $X$ értéke $k$, közelíthető egy azonos várható értékkel, szórással bíró standard normális eloszlás sűrűségfüggvényének segítségével.
- $P(X=k)\approx \frac{1}{\sqrt{2\pi np(1-p)}}e^{-\frac{(k-np)^2}{2np(1-p)}}$
# Nagy számok törvénye
## Átlagra
$$
P(|{\frac{x_1+x_2+\dots+x_n}{n} - m|} \geq \varepsilon)) \leq \frac{\sigma^2}{\varepsilon^2n}
$$
## Relatív gyakoriságra
$$
P(|\frac{k}{n} - p| \geq \varepsilon) \leq \frac{p(1-p)}{\epsilon^2n} \leq \frac{1}{4\varepsilon^2n}
$$
