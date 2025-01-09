#note
## Alapelv
A szétválasztás és korlátozás módszere a [[Visszakereséses módszer]] továbbfejlesztése.
Annyival bővíti a módszert, hogy két extra függvényt vezetünk be
1. Szétválasztási függvény: A részfeladatot még több részfeladatra bontja
2. Korlátozó függvény: Korlátot ad egy optimális megoldásra, ezzel tudjuk, hogy érdemes-e a következő részmegoldásra lépni, vagy sem.
A visszalépéses keresést pedig egy $f_b(szint, E)$ függvénnyel egészítjük ki, ennek feladata, hogy a $szint$ részfeladat megoldása után ad egy felső becslést, hogy a maradék részfeladatok megoldásával lehetséges-e megoldani a teljes feladatot, ez annyit jelent, hogy ha hamis értékkel tér vissza, akkor biztosan nincs megoldás már, ha igaz, akkor még van lehetőség arra hogy van megoldás, de esély van arra is, hogy nincs.
## Általános algoritmus
```pseudocode
eljárás BacktrackSzétKorlát(szint, ref E, ref van)
	i <- 0
	ciklus amíg !van & i < Mszint
		i <- i + 1
		ha ft(szint, (Rszint,i)) akkor
			ha fk(szint, (Rszint,i), E) akkor
				Eszint <- Rszint,i
				ha szint = n akkor
					van <- igaz
				különben
					ha fb(szint, E) akkor
						BacktracSzétKorlát(szint+1, E, van)
					elágazás vége
				elágazás vége
			elágazás vége
		elágazás vége 
	ciklus vége
eljárás vége
```
## Hátizsák probléma megoldása
A hátizsák probléma ezzel a módszerrel is megoldható, hiszen a két kiegészítést a következőképp oldhatjuk meg:
1. Szétválasztás: Az $n$ darab tárgy elhelyezését visszavezetjük két kisebb részfeladatra, azaz, hogy az utolsó elem benne van a zsákban, és ezzel számolunk optimumot a többire, meg azt is feltételezzük, hogy nincs benne, és az alapján számolunk optimumot.
2. Korlátozás:
	- Összeadjuk a rendelkezésre álló tárgyak pakolási értékét
	- Figyelembe vesszük a maradék helyet
### Algoritmus
```pseudocode
eljárás Backtrack(szint, ref E, ref van)
	i <- 0
	ciklus amíg i < Mszint
		i <- i + 1
		ha ft(szint, (Rszint, i)) akkor
			ha fk(szint (Rszint, i), E) akkor
				Eszint <- Rszint,i
				ha szint = n akkor
					ha !van v Jóság(E) > Jóság(O) akkor
						O <- E
					elágazás vége
					van <- igaz
				különben
					ha Jóság(E) + fb(szint, E) > Jóság(O) akkor
						Backtrack(szint+1, E, van)
					elágazás vége
				elágazás vége
eljárás vége
```
## Értékelés
- Rendkívül sok felesleges lépés elkerülhető
- Nem feldolgozott részproblémákat is figyelembe vesz a továbblépés
- Csak akkor használható, ha jól szétválasztható/korlátozható a probléma, ennek kidolgozása bonyolult lehet