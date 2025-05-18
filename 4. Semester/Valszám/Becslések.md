## Jó becslés kritériumai
- A $\Theta_n$ = $\Theta_n(X_1;X_2;\dots;X_3)$ statisztika a $\theta$ paraméter torzítatlan becslése, ha várható értéke megegyezik a becsült elméleti paraméter értékével, azaz: $E(\Theta_n)=\theta$. Egyéb esetben a becslés torzított
- $\theta$ paraméter becslésére szolgáló statisztika torzítása: $B(\Theta_n)=E(\Theta_n)-\theta$
## Konzisztencia
- A $\Theta_n=\Theta_n(X_1;X_2;\dots;X_n)$ statisztika $\theta$ paraméter konzisztens becslése, ha $\Theta_1, \Theta_2, \dots, \Theta_n$ becslés szorzat sztochasztikusan konvergál $\theta$ paraméterhez, azaz ha $\forall  \varepsilon > 0$ esetén:
  $$\lim_{n\to\infty}P(|\Theta_n-\theta|>\varepsilon)=0$$
## Efficiencia
- Ha $\theta$ paraméternek van olyan $\Theta_n^*$ torzítatlan becslése, melynek $\Theta_n$ torzítatlan becslések közül minimális sorozatnégyzete, azaz:
$$D^2(\Theta_n^*)\leq D^2(\Theta_n)$$
## Konfidenciaintervallum
- ($c_1;c_2$) intervallumot X valószínűségi változó $a$ paraméterére vonatkozó (1-$\varepsilon$) megbízhatósági szintű konfidenciaintervallumának nevezzük, ha:
$$P(c_1<a<c_2)=1-\varepsilon$$
### Ismert szórás esetén
$$
\bar{X}\sim\mathcal{N}(m;\frac{\sigma}{\sqrt{n}})
$$
$$
P(-u_\varepsilon < \frac{\bar{X}-m}{\sigma}\sqrt{n} < u_\varepsilon) = 1 - \varepsilon
$$
- $u_\varepsilon$: A konfidenciaintervallum értéke.
### Ismeretlen szórás esetén (t-próba tábla)
$$
X_i \sim \mathcal{N}(m;\sigma) \rightarrow \frac{\bar{X} - m}{S^*}\sqrt{n}\sim t_{n-1}
$$
$$
P(-t_\varepsilon < \frac{\bar{X}-m}{S^*}\sqrt{n}<t_\varepsilon) = 1 - \varepsilon
$$
### Normális eloszlás szórására (Khi-négyzet tábla)
$$
X_i \sim \mathcal{N}(m; \sigma) \rightarrow \frac{(n-1)S^{*^2}}{\sigma^2} \sim \mathcal{X}^2_{1-\frac{\varepsilon}{2}} < \frac{(n-1)S^{*^{2}}}{\sigma^2} < \mathcal{X}^2_{\frac{\epsilon}{2}} = 1 - \varepsilon
$$