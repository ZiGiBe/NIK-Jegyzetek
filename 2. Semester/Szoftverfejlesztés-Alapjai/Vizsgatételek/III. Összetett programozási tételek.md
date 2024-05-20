# Másolás
## Bemenet
- x: T tömb
- n: egész, x hossza
- f: függvény
## Kimenet
- y: T tömb
## Algoritmus
```pseudocode
függvény Másolás(x, n, f)
	y <- Létrehoz(T)[n]
	ciklus i<-1-től n-ig
		y[i] <- f(x[i])
	ciklus vége
	vissza y
függvény vége
```
## Futási idő
- n másolás
- O(n)
# Kiválogatás (külön tömbbe)
## Bemenet
- x: T Tömb
- n: egész, x hossza
- P: logikai függvény
## Kimenet
- y: T tömb
- db: egész, a kiválogatott elemek száma
## Algoritmus
```pseudocode
függvény Kiválogatás(x, n, P)
	y <- Létrehoz(T)[n]
	db <- 0
	ciklus i<-1-től n-ig
		ha P(x[i]) akkor
			db <- db + 1
			y[db] <- x[i]
		elágazás vége
	ciklus vége
	vissza(y,db)
függvény vége
```
## Futási idő
- n vizsgálat
- O(n)
# Kiválogatás (helyben, felülírással)
## Bemenet
- x: T Tömb
- n: egész, x hossza
- P: logikai művelet
## Kimenet
- db: egész, P tulajdonságú elemek száma (felülírt elemek száma)
## Algoritmus
```pseudocode
függvény Kiválogatás(x, n, P)
	db <- 0
	ciklus i<-1-től n-ig
		ha P(x[i]) akkor
			db <- db + 1
			x[db] <- x[i]
		elágazás vége
	ciklus vége
függvény vége
```
## Futási idő
- Legrosszabb esetben n másolás
- n vizsgálat
- O(n)
# Kiválogatás (helyben, felülírás nélkül)
## Bemenet
- x: T tömb
- n: egész, x hossza
- P: logikai művelet
## Kimenet
- db: egész, P tulajdonságú elemek száma
## Algoritmus
```pseudocode
függvény Kiválogatás(x, n, P)
	db <- 0
	ciklus i<-1-től n-ig
		ha P(x[i]) akkor
			db <- db + 1
			x[i] <-> x[db]
		elágazás vége
	ciklus vége
	vissza db
függvény vége
```
## Futási idő
- n vizsgálat
- legrosszabb esetben n csere
- O(n)