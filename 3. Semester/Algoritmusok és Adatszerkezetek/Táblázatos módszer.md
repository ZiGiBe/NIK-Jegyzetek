#note
A táblázatos módszer (dinamikus programozás) egy olyan elv, ami az Oszd meg és uralkodj módszerhez hasonlít, de itt fordítva oldjuk meg az adott problémát, azaz nem felülről/alulra építkezik a módszer, hanem alulról/fefelé, máshogyan fogalmazva megoldjuk először a részproblémákat, majd a konkrét probléma megoldásához érkezünk vele.
## Követelmények
Sajnos a dinamikus programozást nem lehet minden probléma megoldásához alkalmazni. Két feltétele van, ezek:
- Optimális részstruktúrájú legyen a probléma (A probléma optimális megoldása tartalmazza a részfeladatok optimális megoldását)
- Részfeladatoknak átfedőknek kell lennie (merüljön fel többször ugyanaz a részfeladat)
## Hátizsák probléma megoldása
A hátizsák problémát meg lehet oldani a táblázatos módszerrel, mivel
- Optimális részstruktúrájú
- Részfeladatok gyakran átfedik egymást
A megoldás menete a következő:
1. Megvizsgáljuk, hogy az utolsó elemmel, vagy anélkül kapunk-e jobb eredményt
2. Az [[Oszd meg és uralkodj#A hátizsák probléma megoldása|Oszd meg és uralkodj]] módszerben található függvényt használjuk alulról felfelé
### Algoritmus
```pseudocode
függvény DinamikusProgramozás()
	ciklus i<-0-tól n-ig
		F[i, 0] <- 0
	ciklus vége
	ciklus j<-0-tól Wmax-ig
		F[0, j] <- 0
	ciklus vége
	ciklus t<-1-től n-ig
		ciklus h<-1-től Wmax-ig
			ha h>=Wt akkor
				F[t, h] <- max(F[t, h - 1], F[t, h - Wt] + Pt)
			különben
				F[t, h] <- F[t, h - 1]
			elágazás vége
		ciklus vége
	ciklus vége
	vissza F[n, W]
függvény vége
```
## Értékelés
- Nyers erőnél, Oszd meg és uralkodj módszereknél jóval kedvezőbb futásidő
- Nincs rekurzió, emiatt egyszerűbb algoritmus, teljesítmény
- Lehetséges magasabb lépésszám a feljegyzéses módszerhez képest
- Nagyobb tárterületigény