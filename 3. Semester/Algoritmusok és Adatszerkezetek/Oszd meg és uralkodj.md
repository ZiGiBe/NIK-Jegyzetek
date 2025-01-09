#note
## Alapelv
Az oszd meg és uralkodj módszer alapelve az, hogy egy bonyolultabb problémát felosztunk kisebb, egyszerűbb részproblémákig, melynek megoldása nem okoz gondot (azaz már "triviális" megoldásúak).

Általános elv a következő:
1. Ha a megoldandó probléma egyszerű, akkor megoldjuk és visszaadjuk az eredményt.
2. Ha túl bonyolult, akkor
	1. Felosztjuk kisebb részproblémára
	2. Egyesével megoldjuk ezt
	3. Egyesítjük a részeredményeket, amihez előállítjuk a probléma eredményét
## A hátizsák probléma megoldása
A hátizsák problémát fel tudjuk bontani kisebb részproblémák megoldására. Ez pedig a következő:
- Van $n$ darab tárgy, ekkor meg kell vizsgálni, hogy:
	- $n.$ tárgyat nem rakjuk be
	- $n.$ tárgyat berakjuk
- Triviális esetek:
	- Vizsgálandó elemek száma 0.
	- Szabad hely 0.
- Nem triviálisak:
	- Ha az utolsó nem vizsgált tárgy nem fér be, akkor számoljuk, hogy maradék elemek milyen optimális összértékkel helyezhetők el.
	- Ha belefér, akkor megvizsgáljuk, milyen optimális érték érhető el még vele.
Ehhez be kell vezetni egy különleges függvényt, ami az előbb leírt eseteket jellemzi.
$$
f(t, h) = 
\begin{cases}
	0 \text{, ha } h = 0\\
	0 \text{, ha } t = 0 \\
	f(t-1,h)\text{, ha } h > 0 \land t > 0 \land h < w_t \\
	max(f(t-1, h), f(t-1, h - w_t) + p_t) \text{, ha } h > 0 \land t > 0 \land h \geq w_t
\end{cases}
$$
### Algoritmus
```pseudocode
függvény LegjobbRészmegoldás(t, h)
	ha (t = 0) v (h = 0) akkor
		vissza 0
	különben
		Onem <- LegjobbRészmegoldás(t - 1, h)
		ha h >= Wt akkor
			Oigen <- Pt + LegjobbRészmegoldás(t - 1, h - Wt)
			o <- max(Oigen, Onem)
		különben
			o <- Onem
		elágazás vége
		vissza o
	elágazás vége
függvény vége
```
# Értékelés
- Lehet irányítani a keresést, hogy ne nézzen rossz útvonalakat, amivel le lehet szűkíteni a lépésszámot.
- Csak bizonyos szerkezetű problémáknál használható hatékonyan
- Sok felesleges számítást is végezhet.