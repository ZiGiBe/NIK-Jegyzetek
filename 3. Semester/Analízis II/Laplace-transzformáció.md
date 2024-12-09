#note
# A Laplace-transzformáció
$$
 f: [0,\infty[\rightarrow\mathbb{C}, t\rightarrow f(t)
$$
$$
F(s) = \int^\infty_0{f(t)\cdot e^{-st}dt}
$$
$$
D_F = ]0, \infty[ \text{ | ezen intervallumon belül ahol az improrius integrált konvergens}
$$
## Konvergencia
- A Laplace-integrál vagy minden valós számra konvergens, vagy egyre sem, vagy létezik olyan a valós szám, hogy minden s>a számra az integrál konvergens, de minden s\<a-ra divergens
- **Konvergencia elégséges feltétele**: Ha létezik olyan a valós szám, K és t0 pozitív valós szám, hogy
$$
|f(t)| \leq K\cdot e^{at}
$$
	akkor s>a esetén az f függvény Laplace integráltja konvergens
## Tulajdonságok
- Homogén, lineáris
$$
\mathcal{L}[f_1(t) + f_2(t)] = \mathcal{L}[f_1(t)] + \mathcal{L}[f_2(t)]
$$
$$
\mathcal{L}[c\cdot f(t)] = c \cdot \mathcal{L}[f(t)]
$$