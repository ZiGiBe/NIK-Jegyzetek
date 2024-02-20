#note
Homogén bináris relációk esetén két halmazt használunk fel a relációban, melyeknél igaz, hogy A=B, tehát a reláció:
$$
(A, A;R) \rightarrow (A;R); \space D_R = R_R
$$
### Homogén bináris relációk tulajdonságai:
- Reflexív
$$
\forall a\space aRa
$$
- Irreflexív
$$\forall a \space a\not\mathrel{R}b$$
- Szimmetrikus
$$\forall{a}\forall{b} \space  a\mathrel{R}b \implies b\mathrel{R}a$$
- Antiszimmetrikus
$$(a\mathrel{R}b \space\land\space b\mathrel{R}a) \implies a=b$$
- Tranzitív
$$
\forall{a}\forall{b}\forall{c} \space (a\mathrel{R}b)\land(b\mathrel{R}c) \implies (a\mathrel{R}c)
$$
TODO: Gráfok
```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]

\node(a) at (0, 0) {a};
\node(b) at (1, 0) {b};

\path[->] (a) edge (b);

\end{tikzpicture}
\end{document}
```


Azokat a homogén bináris relációkat, melyek reflexívek, szimmetrikusak és tranzitívek **Ekvivalencia relációnak** nevezzük.