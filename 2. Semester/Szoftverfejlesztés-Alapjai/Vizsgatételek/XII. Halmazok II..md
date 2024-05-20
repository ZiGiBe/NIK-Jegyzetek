# Metszet
## Bemenet
- x1: T halmaz
- n1: egész, x1 hossza
- x2: T halmaz
- n2: egész, x2 hossza
## Kimenet
- y: T halmaz, a két halmaz metszete
- db: y hossza
## Algoritmus
```pseudocode
függvény Metszet(x1, n1, x2, n2)
	i <- 1
	j <- 1
	y <- Létrehoz(T)[min(n1,n2)]
	db <- 0
	ciklus amíg (i<=n1) és (j<=n2)
		ha x1[i] = x2[j] akkor
			db <- db + 1
			y[db] <- x1[i]
			i <- i + 1
			j <- j + 1
		különben ha x1[i] > x2[j] akkor
			j <- j + 1
		különben
			i <- i + 1
		elágazás vége
	ciklus vége
	vissza(y,db)
függvény vége
```
# Unió
## Bemenet
- x1: T halmaz
- x2: T halmaz
- n1: x1 hossza
- n2: x2 hossza
## Kimenet
- y: T halmaz, a két halmaz metszete
- db: y hossza
## Algoritmus
```pseudocode
függvény Unió(x1,x2,n1,n2)
	y <- Létrehoz(T)[n1 + n2]
	db <- 0
	n1 <- n1 + 1
	n2 <- n2 + 1
	x1[n1] <- inf
	x2[n2] <- inf
	ciklus amíg i<n1 vagy j<n2
		db <- db + 1
		ha x1[i]=x2[j] akkor
			y[db] <- x1[i]
			i <- i + 1
			j <- j + 1
		különben ha x1[i]>x2[j] akkor
			y[db] <- x2[j]
			j <- j + 1
		különben
			y[db] <- x1[i]
			i <- i + 1
	ciklus vége
	vissza(y,db)
függvény vége
```
## Futási idő
- n1, n2 végig lesz járva, így O(n1+n2)