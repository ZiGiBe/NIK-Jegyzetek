# Maximumkiválasztás, kiválogatás
## Bemenet
- x: T tömb
- n: egész, x hossza

## Kimenet
- y: egész tömb, maximális elemek indexe
- db: y hossza
- maxérték: T maximális elem értéke
## Algoritmus
```pseudocode
függvény MaximumKiválogat(x, n)
	y <- Létrehoz(T)[n]
	db <- 1
	y[1] <- 1
	maxérték <- x[1]
	ciklus i<-2-től n-ig
		ha x[i] > maxérték akkor
			maxérték <- x[i]
			db <- 1
			y[db] <- i
		különben ha x[i] = maxérték akkor
			db <- db + 1
			y[db] <- i
		elágazás vége
	ciklus vége
	vissza(y, db, maxérték)
függvény vége
```
## Futási idő
- n - 1 vizsgálat
- n másolás, ha megegyezik minden elem a maximálissal
- O(n)
# Kiválogatás maximumkiválasztás
## Bemenet
- x: T tömb
- n: egész, x hossza,
- P: logikai függvény
## Kimenet
- van: logikai érték
- max: maximális P tulajdonságú elem indexe
- maxérték: maximális P tulajdonságú elem értéke
## Algoritmus
```pseudocode
függvény KiválogatMaximum(x, n, P)
	max <- 0
	maxérték <- -inf
	ciklus i<-1-től n-ig
		ha x[i] > maxérték és P(x[i]) akkor
			max <- i
			maxérték <- x[i]
		elágazás vége
	ciklus vége
	van <- maxérték > -inf
	ha van akkor
		vissza(van, max, maxérték)
	különben
		vissza(van)
	elágazás vége
függvény vége
```
## Futási idő
- n vizsgálat
- legrosszabb esetben n (minden elem megfelel P tulajdonságnak, és növekvő sorrendben rendezett)
- O(n)