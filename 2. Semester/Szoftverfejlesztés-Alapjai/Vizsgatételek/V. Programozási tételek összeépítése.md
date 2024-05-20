# Bemenet
- x1: T Tömb,
- n1: egész, x1 hossza
- x2: T Tömb
- n2: egész, x2 hossza
- Fontos, hogy T összehasonlítható
# Unió
## Kimenet
- y: T tömb, n1 és n2 uniójának elemei
- db: egész, y hossza
## Algoritmus
```pseudocode
függvény Unió(x1, n1, x2, n2)
	y <- Létrehoz(T)[n1+n2]
	ciklus i<-1-től n1-ig
		y[i] <- x1[i]
	ciklus vége
	
	db <- n1

	ciklus j<-1-től n2-ig
		i <- 1
		ciklus amíg (i<=n1) és (x1[i]!=x2[j])
			i <- i + 1
		ciklus vége
		ha i > n1 akkor
			db <- db + 1
			y[db] <- x2[j]
		elágazás vége
	ciklus vége

	vissza(db, y)
függvény vége
```
## Futási idő
- n1 másolás y tömbbe
- legrosszabb esetben (egy elem sincs benne x1 tömbben): n2\*n1 vizsgálat
- O(n1*\n2)
# Metszet
## Kimenet
- y: T tömb, n1, n2 metszetének elemei
- db: egész, y hossza
## Algoritmus
```pseudocode
függvény Metszet(x1, n1, x2, n2)
	y <- Létrehoz(T)[n1]
	db <- 0
	ciklus i <- 1-től n1-ig
		j <- 1
		ciklus amíg (j <= n2) és (x1[i]!=x2[j])
			j <- j + 1
		ciklus vége
		ha (j <= n2) akkor
			db <- db + 1
			y[db] <- x1[i]
		elágazás vége
	ciklus vége
	vissza(y,db)
függvény vége
```
## Futási idő
- n1\*n2 összehasonlítás legrosszabb esetben (nincs közös elem)
- O(n1\*n2)