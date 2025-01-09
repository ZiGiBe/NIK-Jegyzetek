#note
## Alapelv
A visszalépéses keresés alapelve, hogy egyesével dolgozunk fel részfeladatokat, választunk egy lehetséges részmegoldást, majd a következőt nézzük. Ha találunk olyan részmegoldást, ami használható, akkor néz egy következő részmegoldást, egyéb esetben nem tekintjük megoldásnak az adott részfeladatot.
Fontos, hogy akkor használható leghatékonyabban a módszer, ha
- Több egymást követő (függő) részfeladat megoldásából áll a probléma
- Részfeladatok egy részéből lehet következtetni, hogy nem lehet megoldható a probléma
## Általános alak
- Fontos hogy a változókat áttekintsük ehhez
	- $van$: egy logikai érték, ami azt jelzi, hogy teljes megoldást találtunk-e
	- $E$: A részmegoldás vektor
	- $f_t(szint, r)$: Egy logikai függvény, ami azt jelzi, hogy lehetséges megoldás-e a részfeladatban r
	- $f_k(szint, r, E)$: Egy logikai függvény, ami azt jelzi, hogy lehet-e, r részmegoldást lehet-e választani ebben a szintben
- Algoritmus:
```pseudocode
eljárás Backtracking(szint, ref E, ref van)
	i <- 0
	ciklus amíg !van & i < Mszint
		i <- i + 1
		ha ft(szint, Rszint,i) akkor
			ha fk(szint,(Rszint,i),E) akkor
				Eszint <- Rszint,i
				ha szint = n akkor
					van <- igaz
				különben
					Backtracking(szint+1, E, van)
				elágazás vége
			elágazás vége
		elágazás vége
	ciklus vége
eljárás vége
```
## A hátizsák probléma optimális megoldása visszakereséssel
A hátizsák probléma megoldható a visszakeresés segítségével, mivel:
1. Több egymástól függő részfeladat van (berakható-e a következő elem?)
2. Lehet következtetni részfeladatból arra, hogy nem lesz megoldása a problémának (Túl sok súlyt raktunk a táskába)
Innen egyértelmű, hogy a $f_k$ a következő elven alapul:
$$
f_k(szint, \text{címszerint }E) = Összsúly(E)\leq W_{max}
$$

```pseudocode
eljárás fk(szint, ref E)
	vissza ÖsszSúly(E)<=Wmax
eljárás vége

eljárás Backtrack(szint, ref E, ref O)
	ciklus i<-0-tól 1-ig
		E[szint] <- (i = 0)
		ha fk(szint, E) akkor
			ha szint = n akkor
				ha Összérték(E) > Összérték(O) akkor
					O <- E
				elágazás vége
			különben
				Backtrack(szint+1, E, O)
			elágazás vége
		elágazás vége
	ciklus vége
eljárás vége
```
## Értékelés
- Jól áttekinthető
- Egyértelműen elhanyagolható részfeladatok megoldását nem nézi
- Erőforrásigénye a rekurzió miatt nagy lehet
- Lehet hatékonyabb megoldásokat is találni