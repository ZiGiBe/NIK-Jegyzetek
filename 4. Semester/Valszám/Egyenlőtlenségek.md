## Markov-egyenlőtlenség
Ha $X$ olyan nem negatív értéket felvevő valószínűségi változó, amelynek van várható értéke, és $a$ egy tetszőleges pozitív valós szám, akkor:
$$
P(X\geq a)\leq \frac{E(X)}{a}
$$
$$
P(X<a) \geq 1-\frac{E(X)}{a}
$$
## Csebisev-egyenlőtlenség
A várható értéktől a szórás sokszorosával való eltérés valószínűségének felső korlátja van, míg a sokszorostól kisebb eltérés pedig alsó korlátos.
Legyen $X$ olyan valószínűségi változó, aminek van várható értéke, szórása, és legyen $\lambda$ egy tetszőleges pozitív szám, ilyenkor:
$$
P(|X-E(X)| \geq \lambda \cdot D(X)) \leq \frac{1}{\lambda^2}
$$
$$
P(|X-E(X)|<\lambda\cdot D(X)) > 1 - \frac{1}{\lambda^2}
$$
## Nagy számok törvényei
### Az átlagra
Legyenek $X_1,X_2,\dots,X_n$ független valószínűségi változók azonos várható értékkel, és szórással. Ekkor:
$$
P\left( \frac{X_1+X_2+\dots+X_n}{n} \geq \varepsilon \right) \leq \frac{\sigma^2}{\varepsilon^2\cdot n}
$$
$$
P\left(\frac{X_1+X_2+ \dots +X_n}{n} \leq \varepsilon \right) > 1 - \frac{\sigma^2}{\varepsilon^2\cdot n}
$$
### Relatív gyakoriságra
A nagy számok törvénye a relatív gyakoriságra azt jelenti, hogy egy relatív gyakoriság nem térhet el nagyon az elméleti valószínűségtől.

Végzünk $n$ darab független kísérletet $p$ valószínűséggel $A$ esemény megfigyelésére, ekkor feltesszük, hogy $A$ esemény $k$ alkalommal következik be. Ekkor tetszőleges $\varepsilon$ ($\varepsilon>0$) esetén:
$$
P\left( \left| \frac{k}{n} - p \right| \geq \varepsilon \right) \leq \frac{p\cdot (1-p)}{\varepsilon^2 \cdot n}
$$
$$
P\left(\left| \frac{k}{n}-p \right| < \varepsilon \right) \geq 1 - \frac{p\cdot (1-p)}{\varepsilon^2\cdot n}
$$