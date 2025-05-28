## u-próba
### Egymintás
El akarjuk dönteni, hogy $n$ elemű $\hat{m}_n$ mintaátlagú statisztikai minta elméleti várható értéke lehet-e $m_0$.
#### Amikor ismert a szórás
Ekkor $H_0$ hipotézist feltételezzük, hogy helyes. A mintaelemek $\sigma$ szórású, $m_0$ várható értékű valószínűségi változók, ilyenkor
$$
u_p = \frac{\hat{m}_n-m_0}{\frac{\sigma}{\sqrt{n}}}
$$
próbastatisztika standard normális eloszlású.
#### Amikor nem ismert a szórás
Ha a szórás nem ismert, de az elemszám $n\geq 30$, akkor a mintaátlag szórását a $\hat{s}_n$-el becsüljük, és így a
$$
u_p = \frac{\hat{m}_n-m_0}{\frac{\hat{s}_n}{\sqrt{n}}}
$$
próbastatisztika standard normális eloszlású.

### Kétmintás
## t-próba
### Egymintás
Egy $n$ elemű $\hat{m}_n$ mintaátlagú statisztikai minta várható értéke lehet-e $m_0$. Amennyiben a $\sigma$ szórás nem ismert és $n$ elemszáma kicsi, akkor $$
t_p=\frac{\hat{m}_n-m_0}{\frac{\hat{s}_n}{\sqrt{n}}}
$$
próbastatisztika (n-1) szabadsági fokú, Student-eloszlású
### Kétmintás