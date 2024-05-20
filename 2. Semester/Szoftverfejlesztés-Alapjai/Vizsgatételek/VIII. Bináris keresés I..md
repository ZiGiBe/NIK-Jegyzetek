# Rendezettség
## Bemenet
- x: T tömb
- n: egész, x hossz
## Kimenet
- o: logikai érték
## Algoritmus
```pseudocode
függvény RendezettE(x, n)
	i <- 1
	ciklus amíg (i<n) és (x[i]<=x[i + 1])
		i <- i + 1
	ciklus vége
	o <- i >= n
	vissza o
függvény vége
```
## Futási idő
- n - 1 összehasonlítás
- O(n)
# Bináris keresés
## Bemenet
- x: T tömb
- n: egész, x hossza,
- k: T, keresett érték
## Kimenet
- van: logikai érték
- idx: egészérték, keresett érték indexe
## Algoritmus
```pseudocode
függvény BinárisKeresés(x, n, k)
	bal <- 1
	jobb <- n
	center <- bal + jobb / 2
	ciklus amíg (bal<=jobb) és (x[center]!=k)
		ha x[center] > k akkor
			jobb <- center - 1
		különben
			bal <- center + 1
		elágazás vége
		center <- bal + jobb / 2
	ciklus vége
	van <- bal <= jobb
	ha van akkor
		idx <- center
		vissza(van,idx)
	különben
		vissza van
	elágazás vége
```
## Futási idő
- legrosszabb esetben 1 + log2(n) vizsgálat
- log2(n)-szer felezhető egy n elemű tömb
- O(log(n))