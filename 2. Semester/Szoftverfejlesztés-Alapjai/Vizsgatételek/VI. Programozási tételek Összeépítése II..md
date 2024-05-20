## Másolás, maximumkiválasztás
## Bemenet
- x: T tömb
- n: egész, x hossza
- f: függvényművelet
## Kimenet
- max: egész, maximális elem indexe
- maxérték: T, Maximális elem
## Algoritmus
```pseudocode
függvény MásolMaximum(x, n, f)
	max <- 1
	maxérték <- f(x[1])
	ciklus i<-2-től n-ig
		segéd <- f(x[i])
		ha segéd > maxérték akkor
			max <- i
			maxérték <- segéd
		elágazás vége
	ciklus vége
	vissza(max, maxérték)
függvény vége
```
## Futási idő
- n - 1 Vizsgálat
- n másolás
- O(n)
## Megszámolás, keresés
## Bemenet
- x: T tömb
- n: egész, x hossza
- P: logikai függvény
- k: egész, keresett darabszám
## Kimenet
- van: logikai, megtalálható-e k elem a tömbben
- idx: egész, k előfordulású elem indexe
## Algoritmus
```pseudocode
függvény MegszámolKeres(x, n, P, k)
	db <- 0
	i <- 1
	ciklus amíg (i <= n) és (db<k)
		ha P(x[i]) akkor
			db <- db + 1
		elágazás vége
		i <- i + 1
	ciklus vége
	van <- db = k
	ha van akkor
		vissza(van,idx)
	különben
		vissza van
	elágazás vége
függvény vége
```
## Futási idő
- n vizsgálat legrosszabb esetben
- legjobb esetben 0 vizsgálat (k = 0)
- O(n)