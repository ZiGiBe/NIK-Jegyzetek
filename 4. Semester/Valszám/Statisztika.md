## Statisztikai minta
$X$ valószínűségi változóval azonos eloszlású, független $X_1, X_2, \dots , X_n$ valószínűségi változók összességét statisztikai mintának nevezzük.
## Statisztikai függvény
Az $X_1, X_2, \dots , X_n$ valószínűségi változókat a valós számok halmazára képező $\hat{\alpha} : \mathbb{R} \to \mathbb{R}$  függvényt statisztikának, vagy másnéven statisztikai függvénynek nevezzük.
## Mintaátlag (Empirikus közép)
Az $X_1, X_2, \dots , X_n$ mintaelemek mintaátlaga:
$$
\bar{X} = \frac{1}{n}\cdot\sum^n_{i=1} X_i = \frac{X_1+X_2 + \dots{} + X_n}{n}
$$
## Tapasztalati szórásnégyzet (empirikus szórásnégyzet)
$X_1, X_2, \dots , X_n$ mintaelemek tapasztalati szórásnégyzete a mintaelemek mintaátlagtól való eltérésének négyzetes közepét értjük, azaz:
$$
\sigma^2_n=\frac{1}{n}\cdot\sum^n_{i=1}(X_i-\hat{m}_n)^2=\frac{(X_1-\hat{m}_n)^2 + (X_2-\hat{m}_n)^2 + \dots{} + (X_n-\hat{m}_m)^2}{n}
$$
## Korrigált tapasztalati szórásnégyzet
$$
\hat{s}^2_n=\frac{1}{n-1}\cdot\sum^n_{i=1}(X_i-\hat{m}_n)=\frac{(X_1-\hat{m}_n)^2 + (X_2-\hat{m}_n)^2+\dots{}+(X_n-\hat{m}_n)^2}{n-1}
$$
## Medián
$X_1^*, X_2^*, \dots, X_n^*$ rendezett mintaelemek mediánja
$$
\begin{array}{ll}
\frac{X^*_k+K^*_{k+1}}{2}, && \mbox{ha }n=2\cdot k \\
X^*_{k+1}, && \mbox{ha } n = 2 \cdot k + 1
\end{array}
$$
## Módusz
A módusz a statisztikai mintában leggyakrabban előforduló mintalem.
## Statisztikában használt eloszlások
### $\chi^2$ eloszlás
Legyenek $X_1, X_2, \dots, X_n$ független, standard normális eloszlású változók. Ekkor a belőlük képzett $\chi^2=X^2_1+X^2_2+\dots+X^2_n$ valószínűségi változó eloszlását $n$ szabadsági fokú $\chi^2$-eloszlásnak nevezzük.
### Student-féle t-eloszlás
Legyenek $Y$, és $X_1, X_2, \dots, X_n$ független, standard normális eloszlású valószínűségi változók, ekkor a belőlük képzett
$$
t_n = \frac{Y}{\sqrt{\frac{X_1^2+X_2^2+\dots{}+X_n^2}{n}}}
$$
valószínűségi változó eloszlását $n$ szabadsági fokú Student-eloszlásnak nevezzük.