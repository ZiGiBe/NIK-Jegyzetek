#note 
Parciális rendezésnek nevezzük azt a homogén bináris relációt, melyek reflexívek, tranzitívek és antiszimmetrikusak.

Ilyen reláció például:
$$
(R , \leq)
$$
---
### Hasse-diagram
- Nincsenek hurkok
- a <= b esetén b feljebb van a-tól
- A tranzitivitásból jövő nyilakat nem rajzoljuk be

Példa egy diagramra:
$$
A = \{1, 2, 3, 4, 6, 12\}
$$
$$
(A, \mathrel{R}), \space R=x|y
$$

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.2]

\node (one) at (0,0) {1};
\node (three) at (1, 1) {3};
\node (two) at (-1, 1) {2};
\node (four) at (-2, 2) {4};
\node (six) at (0, 2) {6};
\node (twelve) at (-1, 3) {12};

\draw (one) -- (two) -- (four) -- (twelve);
\draw (one) -- (three) -- (six) -- (twelve);
\draw (two) -- (six);

\end{tikzpicture}
\end{document}
```
---
### Legnagyobb elem, Legkisebb elem
Parciális rendezésben a legnagyobb elemre igaz, hogy:
$$
l\in{A}
$$
$$
(\forall{x\in{A}}) \space x<l
$$
A legkisebb elemre igaz pedig, hogy:
$$
k\in{A}
$$
$$
\forall{(x\in{A})} x \geq k
$$
### Maximális, minimális
Parciális rendezésben a maximálisra igaz, hogy:
$$
m\in{A}
$$
$$
\forall{x} \space m\leq{x}\implies{x=m}
$$
A minimálisra igaz, hogy:
$$
n\in{A}
$$
$$
\forall{x} \space x\leq{n}\implies{x=n}
$$
### Felső, alsó korlát
**Felső korlát**:
$$
f\in{(H\subseteq{A})}
$$
$$
\forall{(h\in{H})} \space h\leq{f}
$$
**Alsó korlát:**
$$
k\in{(H\subseteq{A})}
$$
$$
\forall{(l\in{H})} \space l\geq{k}
$$
---
- Szuprémum: Legkisebb felső korlát
- Infimum: Legnagyobb alsó korlát
### Parciális rendezés háló
- Parciális rendezés hálóról beszélünk, ha:
$$
\forall{a}\forall{b}
$$
$$
\exists{\sup(a,b) \land{\inf(a,b)}}
$$
### Szuprémum, Infimum műveletek
- Idempotens:
$$

\begin{matrix}
	\sup(a,a) = a \\
	\inf(a,a) = a
\end{matrix}

$$
- Kommutatív:
$$
\begin{matrix}
	\sup(a,b) = \sup(b,a) \\
	\inf(a,b) = \inf(b,a)
\end{matrix}
$$
- Disztributív:
$$
\begin{matrix}
	\sup(a, \sup(b,c)) = \sup(\sup(a,b), c) \\
	\inf(a, \inf(b,c)) = \inf(\inf(a,b), c)
\end{matrix}
$$
- Abszorptív:
$$
\begin{matrix}
	\sup(a,\inf(a,b)) = a \\
	\inf(a, \sup(a,b)) = a
\end{matrix}
$$