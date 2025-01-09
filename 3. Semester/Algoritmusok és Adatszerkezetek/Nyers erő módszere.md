#note
A nyers erő módszere egy könnyen alkalmazható megoldási stratégia. Egyetlen követelménye, hogy véges mennyiségű megoldás legyen a feladathoz.
# Elv
1. Következő megoldás kiválasztása/generálása
2. Megoldásjelölt elfogadhatóságának vizsgálata
3. Ha igen, akkor ellenőrizzük, hogy a megoldás jósága jobb-e, mint az eddigi legjobb. Ha igen akkor ez lesz a legjobb
4. Ezt addig folytatjuk, ameddig nem fogyunk el megoldásjelöltekből
# Algoritmus
```pseudocode
függvény BruteForce()
	o <- Generátor(1)
	ciklus i<-2-től m-ig
		x <- Generátor(i)
		ha Jóság(x) > Jóság(o) akkor
			o <- x
		elágazás vége
	ciklus vége
	vissza o
függvény vége
```
# Értékelés
- Gyorsan implementálható, megérthető
- Minden esetben használható, amikor véges számú megoldás van a feladathoz
- Ha nincs támpont, akkor gyakran csak ezt a megoldási módszert lehet használni
- Kis tárhelyigény
- Erőforrásigény nagy
- Hosszú lefutási idő