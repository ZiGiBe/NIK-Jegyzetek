# Különbség
## Bemenet
- x1: T halmaz
- n1: egész, x1 hossza
- x2: T halmaz
- n2: egész, x2 hossza
## Kimenet
- y: T halmaz, a két halmaz különbsége
- db: y hossza
## Algoritmus
```pseudocode
függvény Különbség(x1, n1, x2, n2)
	y <- Létrehoz(T)[n1]
	db <- 0
	i <- 1
	j <- 1
	ciklus amíg (i <= n1) és (j <= n2)
		ha x1[i] < x2[j] akkor
			db <- db + 1
			y[db] <- x1[i]
			i <- i + 1
		különben ha x1[i] > x2[j] akkor
			j <- j + 1
		különben
			i <- i + 1
			j <- j + 1
		elágazás vége
	ciklus vége
	ciklus amíg (i <= n1)
		db <- db + 1
		y[db] <- x[i]
		i <- i + 1
	ciklus vége
	vissza(y, db)
függvény vége
```
## Futási idő
- O(n1)
# Szimmetrikus differencia
## Bemenet
- x1: T halmaz
- x2: T halmaz
- n1: egész, x1 hossza
- n2: egész x2 hossza
## Kimenet
- y: T halmaz, x1 és x2 szimmetrikus  különbsége
- db <- y hossza
## Algoritmus
```pseudocode
függvény SzimmetrikusDiff(x1, n1, x2, n2)
	y <- Létrehoz(T)[n1+n2]
	db <- 0
	i <- 1
	j <- 1
	ciklus amíg (i <= n1) és (j <= n2)
		ha x1[i] = x2[j] akkor
			i <- i + 1
			j <- j + 1
		különben ha x1[i]<x2[j] akkor
			db <- db + 1
			y[db] <- x1[i]
			i <- i + 1
		különben
			db <- db + 1
			y[db] <- x2[j]
			j <- j + 1
	ciklus vége
	ciklus amíg (i <= n1)
		db <- db + 1
		y[db] <- x1[i]
	ciklus vége
	ciklus amíg (j <= n2)
		db <- db + 1
		y[db] <- x2[j]
	ciklus vége
	vissza(y, db)
függvény vége
```
## Futási idő
- O(n1+n2)