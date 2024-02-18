#note
## Aluláteresztő szűrő
```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[]
\draw (0,0) to[short, *-] (1,0)
	  (1,0) to[R, l=$R$] (5,0)
	  (5,0) to[C,a=$\downarrow U_{be}$ , l=$C \downarrow U_{ki}$] (5,-3)
	  (5,0) to[short, *-] (8,0)
	  (8,0) to[short, *-] (8,0)
	  (5,-3) to[short, *-] (8,-3)
	  (0,-3) to[short, *-] (5,-3)
	  (8,-3) to[short,*-] (8,-3)
;
\end{circuitikz}
\end{document}
```
- Amplitúdó kiszámítása
$$
A_U = \frac{U_{ki}}{U_{be}} = \frac{1}{1+j\omega RC}
$$
$$
|A_U| = 20lg(\frac{1}{1+j\omega^2R^2C^2})^\frac{1}{2}
$$
$$
[A_U]=db
$$
- Bode-diagram
```tikz
	\begin{document}
	\begin{tikzpicture}[domain=0:10]
	\draw[->] (-0.2,0) -- (10.2,0) node[right] {$lg(f)$};
    \draw[->] (0,-0.2) -- (0,5.2) node[above] {$A_U$};
    \draw[color=red, domain=0.1:10] plot(\x, {1/(\x)});
    \end{tikzpicture}
    \end{document}
```
