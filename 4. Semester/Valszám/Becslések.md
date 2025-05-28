## Pontbecslések
Pontbecslés esetén a változó értékét a mintából számított konkrét értékkel becsüljük. Legnagyobb valószínűség elve esetén azt keressük, hogy az eloszlás mely paraméterei mellett kapható meg kísérlet során legnagyobb valószínűséggel az adott minta.

$$
\begin{array}{lll}
\hat{p} = \hat{P(A)}=\frac{k_i}{n} && 
\hat{m}=\hat{E(X)}=\bar{X} &&
\hat{\sigma^2} = \hat{D^2(X)}=S^{*^2}_n &&
\end{array}
$$

## Jó becslés kritériumai
### Torzítatlanság
A $\Theta_n=\Theta_n(X_1;X_2;\dots;X_n)$ statisztika $\theta$ paraméter torzítatlan becslése, ha várható értéke megegyezik a becsült elméleti paraméter értékével, amennyiben nem, akkor a becslés torzított.
#### Torzítás:
$$
B(\Theta_n) = E(\Theta_n) - \theta
$$
Ha $\Theta_n$ torzítás:
- Pozitív, akkor átlagosan felülbecsüli az elméleti paraméter értékét.
- Nulla, akkor átlagosan jól becsüli az elméleti paraméter értékét.
- Negatív, akkor átlagosan alulbecsüli az elméleti paraméter értékét.
### Konzisztencia
$\Theta_n=\Theta_n(X_1;X_2;\dots;X_n)$ statisztika $\theta$ paraméter konzisztens becslése, ha $\Theta_1;\Theta_2;\dots;\Theta_n;\dots$ becsléssorozat sztochasztikusan konvergál $\theta$ paraméterhez, tehát $\forall \varepsilon > 0$ esetén:
$$
\lim_{n\to\infty}(P|\Theta_n-\theta|>\varepsilon) = 0
$$
### Efficiencia
Ha $\theta$ paraméternek van olyan $\Theta_n^*$ torzítatlan becslése, amelynek $\Theta_n$ torzítatlan becslések közül minimális a szórásnégyzete, tehát:
$$
D^2(\Theta^*_n) \leq D^2(\Theta_n)
$$
akkor a $\Theta_n^*$ statisztika $\theta$ paraméter efficiens becslése
## Intervallumbecslés
$(c_1;c_2)$ intervallumot $X$ valószínűségi változó $a$ paraméterére vonatkozó $(1-\varepsilon)$ megbízhatósági szintű konfidenciaintervallumának nevezzük, ha:
$$
P(c_1<a<c_2) = 1 - \varepsilon
$$
$$
P(a\leq c_1) = P(a\geq c_2) = \frac{\varepsilon}{2}
$$
### Ismert ($\sigma$) szórás esetén (empirikus szórás)
$X$ ismeretlen $m$ várható értékű, de ismert $\sigma$ szórású valószínűségi változó megfigyelésére nagy $n$ elemszámú mintát veszünk, ahonnan a mintaátlag $\hat{m}_n$. Ilyenkor a várható értékre vonatkozó $p=1-\varepsilon$ megbízhatósági szintű konfidencia-intervallum:
$$
\left[ \hat{m}_n-u\frac{\sigma}{\sqrt{n}}; \hat{m}_n+u\frac{\sigma}{\sqrt{n}}  \right]
$$
$$
\Phi(u) = \frac{1+p}{2}
$$
### Ismeretlen ($s^*$) szórás esetén
$$
\left[ \bar{X} - t_\varepsilon \frac{s^*}{\sqrt{n}}; \bar{X}+t_\varepsilon \frac{s^*}{\sqrt{n}}  \right]
$$
### Intervallum szórásra
$$
\left[\sqrt{n-1}\frac{s^*_n}{\sqrt{c_2}}; \sqrt{n-1}\frac{s^*_n}{\sqrt{c_1}} \right]
$$$c_1$: $\chi^2$ táblázat $n-1$ sora, $1-\frac{\varepsilon}{2}$ oszlopa.
$c_2$: $\chi^2$ táblázat $n-1$ sora, $\frac{\varepsilon}{2}$ oszlopa.