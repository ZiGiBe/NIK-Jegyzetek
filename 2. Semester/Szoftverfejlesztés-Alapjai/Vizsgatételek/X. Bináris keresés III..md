# Alsóhatár
## Bemenet
- x: T tömb
- n: egész, x hossza
- k: alsó határhoz keresett érték
## Kimenet
- idx: egész, alsó határ
## Algoritmus
```pseudocode
függvény AlsóHatár(x, n, k)
	bal <- 1
	jobb <- n
	idx <- 0
	center <- bal + jobb / 2
	ciklus amíg(bal<=jobb)
		ha x[center] >= k akkor
			idx <- center
			jobb <- center - 1
		különben
			bal <- center + 1
		elágazás vége
		center <- bal + jobb / 2
	ciklus vége
	vissza idx
függvény vége
```
## Futási idő
- log2(n) felezés
- O(log(n))
# Felsőhatár
## Bemenet
- x: T tömb
- n: egész, x hossza
- k: T, felsőhatárhoz keresett elem
## Kimenet
- idx: felső határ indexe
## Algoritmus
```pseudocode
függvény BinárisKeresés(x, n, k)
	bal <- 1
	jobb <- n
	idx <- n + 1
	center <- bal + jobb / 2
	ciklus amíg (bal<=jobb)
		ha x[center] > k akkor
			idx <- center
			jobb <- center - 1
		különben
			bal <- center + 1
		elágazás vége
		center <- bal + jobb / 2
	ciklus vége
	vissza idx
függvény vége
```
## Futási idő
- log2(n) összehasonlítás
- O(log(n))
