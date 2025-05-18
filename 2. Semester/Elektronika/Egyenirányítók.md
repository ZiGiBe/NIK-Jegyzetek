# Egyutas egyenirányító
## Egyutas egyenirányító pufferkondenzátorral
```tikz
\usepackage{circuitikz}
\begin{document}
	\begin{circuitikz}
	% Paths, nodes and wires:
	\draw (9, 6) to[european resistor, l={$R1$}, label distance=0.02cm] (9, 3);
	\draw (3, 6) to[empty diode, l={$D1$}, label distance=0.02cm] (6, 6);
	\draw (6, 6) to[ecapacitor, l={$C1$}, label distance=0.02cm] (6, 3);
	\draw node[transformer, cute, xscale=1.43, yscale=1.43] at (1.499, 4.499) {};
	\draw (6, 6) -- (9, 6);
	\draw (9, 3) -- (6, 3);
	\draw (6, 3) -- (3, 3);
	\draw node[ocirc] at (0, 6) {};
	\draw node[ocirc] at (-0.003, 2.997) {};
	\end{circuitikz}
\end{document}
```
## Egyutas egyenirányító
```tikz
\usepackage{circuitikz}
\begin{document}
	\begin{circuitikz}
	\draw (6.75, 6) to[european resistor, l={$R1$}, label distance=0.02cm] (6.75, 3);
	\draw (3, 6) to[empty diode, l={$D1$}, label distance=0.02cm] (6, 6);
	\draw node[transformer, cute, xscale=1.43, yscale=1.43] at (1.499, 4.499) {};
	\draw (6, 3) -- (3, 3);
	\draw node[ocirc] at (0, 6) {};
	\draw node[ocirc] at (-0.003, 2.997) {};
	\draw (6.75, 6) -- (6, 6);
	\draw (6, 3) -- (6.75, 3);
	\end{circuitikz}
\end{document}
```
