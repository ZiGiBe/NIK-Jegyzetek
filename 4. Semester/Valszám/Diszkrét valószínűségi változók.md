**Valószínűségi változó:** Ha egy kísérlettel kapcsolatos elemi események mindegyikéhez egyértelműen hozzárendelünk egy-egy valós számot, akkor az elemi események $\Omega$ halmazán egy $X: \Omega \to \mathbb{R}$ függvényt értelmezünk, és ezt valószínűségi változónak nevezzük.
**A valószínűségi változó eloszlása:** A valószínűségi változóban meghatározzuk, hogy a valószínűségi változó milyen értékeket milyen valószínűséggel vesz fel. Ezeket megadhatjuk:
1. Felsorolás
2. Táblázattal
3. Grafikonnal
4. Képlettel
**Eloszlásfüggvény:** $X$ valószínűségi változó eloszlásfüggvényének nevezzük azt az $F$ függvényt, ami minden valós $x$ értékhez hozzárendeli annak valószínűségét, hogy az $X$ valószínűségi változó $x$-nél kisebb értéket vesz fel, tehát: $F:\mathbb{R}\to\mathbb{R}, F(X)=P(X<x)$.
Tulajdonságok
- $D_F=\mathbb{R};R_F\subseteq [0;1]$
- Monton növekedő
- Balról minden pontban folytonos, kivéve egy $\aleph_0$ pontot, ahonnan jobbról nem folytonos.
- $\lim_{x\to -\infty}F(X)=0$
---
%% Őszintén fogalmam sincs hogy Kárász ide miért nem rakta a tételsorban a diszkrét valószínűségi változót, mint kérdés, úgyhogy itt van, mielőtt elfelejteném %%
## Diszkrét valószínűségi változó
Akkor nevezünk egy valószínűségi változót diszkrétnek, ha lehetséges értékeinek halmaza megszámlálható. $X$ diszkrét valószínűségi változó lehetséges értékeihez tartozó bekövetkezési valószínűségek összességét $X$ eloszlásának nevezzük, lehetséges értékei az $x_k$ számok, akkor $X$ eloszlása a $p_k=P(X=x_k)$ bekövetkezési valószínűségek összessége.
- **Módusz:** A diszkrét valószínűségi változó $x_i$ értéke, ahol $p_i$ maximális.
- **Medián**: A változó azon $x_i$ értéke, ahol $P(X\leq x)$ és $P(X\geq x)$ egyaránt legalább $\frac{1}{2}$.
- **Várható érték**: A diszkrét valószínűségi változó várható értéke: $E(X)=\sum_ip_ix_i=\sum_{x\in R_X}xf(x)$
  Tulajdonságai:
	  - $E(aX+b)=aE(X)+b$
	  - $E(X+Y)=E(X)+E(Y)$
- **Szórás**: $X$ valószínűségi változó szórásán $(X-E(X))^2$ várható értékének négyzetgyökét értjük, azaz:
  $$
	D(X)=\sqrt{E[(X-E(X))^2]}
   $$
 %% Ismételten fogalmam sincs Kárász mire gondol a szórás, és várható érték tulajdonságain, szóval arra nincs semmim (könyvben sem) %%
