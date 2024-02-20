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

### Tulajdonságok gráfjai (Példák):
- Reflexív
```tikz
\begin{document}
\begin{tikzpicture}[scale=5, line width=2pt]

\node(a) at (0, 0) {\huge a};
\node(b) at (1, 0) {\huge b};
\node(c) at (0, 1) {\huge c};
\node(d) at (1,1) {\huge d};

\path[->] (a) edge (b);
\path[->] (a) edge [loop left] (b);
\path[->] (b) edge [loop right] (b);
\path[->] (c) edge [loop above] (c);
\path[->] (d) edge [loop below] (d);



\end{tikzpicture}
\end{document}
```
- Irreflexív
```tikz
\begin{document}

	\begin{tikzpicture}[scale=5, line width=2pt]
		\node (a) at (0,0) {\huge a};
		\node (b) at (0,1) {\huge b};
		\node (c) at (1,0) {\huge c};
		\node (d) at (1,1) {\huge d};

		\path[->] (a) edge (b);
		\path[->] (c) edge (b);

	\end{tikzpicture}

\end{document}
```
- Szimmetrikus
```tikz
\begin{document}

	\begin{tikzpicture}[scale=5, line width=2pt]
		\node(a) at (0,0) {\huge a};
		\node(b) at (1,0) {\huge b};
		\node(c) at (0,1) {\huge c};
		\node(d) at (1,1) {\huge d};


		\path[->]
			(a) edge [bend left] (b)
				edge [bend left](c);
		\path[->]
			(b) edge [bend left] (a)
				edge[loop above] (b);
		\path[->]
			(c) edge [bend left] (a);
	\end{tikzpicture}

\end{document}
```
- Antiszimmetrikus
```tikz
\begin{document}

\begin{tikzpicture}[scale=5, line width=2pt]

\node(a) at (0,0) {\huge a};
\node(b) at (1,0) {\huge b};
\node(c) at (0,1) {\huge c};
\node(d) at (1,1) {\huge d};

\path[->](a)
	edge (b)
	edge (c)
	edge[loop below] (a);

\path[->](d)
	edge(a)
	edge[loop above](d);

\end{tikzpicture}

\end{document}
```
- Tranzitív
```tikz
\begin{document}

\begin{tikzpicture}[scale=5, line width=2pt]

\node(a) at (0,0) {\huge a};
\node(b) at (0,1) {\huge b};
\node(c) at (1,0) {\huge c};
\node(d) at (1,1) {\huge d};

\path[->](a)
	edge (b)
	edge[bend right] (c);
\path[->](b)
	edge (c);

\end{tikzpicture}

\end{document}
```

Azokat a homogén bináris relációkat, melyek reflexívek, szimmetrikusak és tranzitívek **Ekvivalencia relációnak** nevezzük.