# Bemenet minden algoritmusnál
- x: T tömb
- n: egész, x hossza
- P: logikai függvény
# Szétválogatás
## Kimenet
- y1, y2: T tömb, y1 tartalmazza a P-hez megfelelő elemeket, míg y2 a nem megfelelőket.
- db1, db2: y1 hossza, y2 hossza
## Algoritmus
```pseudocode
függvény Szétválogatás(x, n, P)
	y1 <- Létrehoz(T)[n]
	y2 <- Létrehoz(T)[n]
	db1 <- 0
	db2 <- 0
	ciklus i<-1-től n-ig
		ha P(x[i]) akkor
			db1 <- db1 + 1
			y1[db1] <- x[i]
		különben
			db2 <- db2 + 1
			y2[db2] <- x[i]
		elágazás vége
	ciklus vége
	vissza(y1,db1,y2,db2)
függvény vége
```
## Futási idő
- n másolás, vizsgálat
- O(n)
- Nem hatékony memória szempontjából
# Szétválogatás (egy tömbbe)
## Kimenet
- y: T tömb
- db: egész, db értékig minden tömbelem megfelel a P tulajdonságnak, míg annál nagyobb elemek nem
## Algoritmus
```pseudocode
függvény Szétválogatás(x, n, P)
	db <- 0
	jobb <- n + 1
	y <- Létrehozás(T)[n]
	ciklus i<-1-től n-ig
		ha P(x[i]) akkor
			db <- db + 1
			y[db] <- x[i]
		különben
			jobb <- jobb - 1
			y[jobb] <- x[i]
		elágazás vége
	ciklus vége
	vissza(y, db)
függvény vége
```
## Futási idő
- Hasonlít a két tömbös futási idejére
- O(n)
# Szétválogatás (helyben)
## Kimenet
- db: egész, minden db értékig megfelel P tulajdonságnak
## Algoritmus
```pseudocode
függvény SzétválogatásHelyben(címszerint x, n, P)
	bal <- 1
	jobb <- n
	segéd <- x[1]
	ciklus amíg bal < jobb
		ciklus amíg bal < jobb és !P(x[jobb])
			jobb <- jobb - 1
		ciklus vége
		ha bal < jobb akkor
			x[bal] <- x[jobb]
			bal <- bal + 1
			ciklus amíg bal < jobb és P(x[bal])
				bal <- bal + 1
			ciklus vége
			ha bal < jobb akkor
				x[jobb] <- x[bal]
				jobb <- jobb - 1
			elágazás vége
		elágazás vége
	ciklus vége
	x[bal] <- segéd
	ha P(x[bal]) akkor
		db <- bal
		vissza db
	különben
		db <- bal - 1
		vissza db
	elágazás vége
függvény vége
```
## Futási idő
- n vizsgálat
- Legrosszabb eset: fordított szétválogatás, ilyenkor n + 1 mozgatás
- O(n)