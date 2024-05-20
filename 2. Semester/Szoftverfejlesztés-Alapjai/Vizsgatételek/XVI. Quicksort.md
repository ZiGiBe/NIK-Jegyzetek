# Szétválogatás támpont alapján
## Bemenet
- x: T tömb
- bal: egész, x résztömb/tömbnek bal széle
- jobb: egész, x résztömb/tömbnek jobb széle
## Kimenet
- idx: egész, a támpont indexe, az az elem, amelyik alapján szétválogattuk a tömböt
## Algoritmus
```pseudocode
függvény Szétválogatás(címszerint x, bal, jobb)
	segéd <- x[bal]
	ciklus amíg (bal < jobb)
		ciklus (bal < jobb) és (x[jobb] > segéd)
			jobb <- jobb - 1
		ciklus vége
		ha bal < jobb akkor
			x[bal] <- x[jobb]
			bal <- bal + 1
			ciklus (bal < jobb) és (x[bal] <= segéd)
				bal <- bal + 1
			ciklus vége
			ha bal < jobb akkor
				x[jobb] <- x[bal]
				jobb <- jobb - 1
			elágazás vége
		elágazás vége
	ciklus vége
	idx <- bal
	x[idx] <- segéd
	vissza idx
függvény vége
```
## Futási idő
- [[IV. Összetett programozási tételek II.#Szétválogatás (helyben)#Futási idő|Lásd itt]]
# Quicksort
## Bemenet
- x: T tömb
- bal: x résztömbjének bal széle
- jobb: x résztömbjének jobb széle
## Algoritmus
```pseudocode
eljárás QuickSort(címszerint x, bal, jobb)
	idx <- Szétválogat(x, bal, jobb)
	ha idx > bal + 1 akkor
		QuickSort(x, bal, idx - 1)
	ha idx < jobb - 1 akkor
		QuickSort(x, idx + 1, jobb)
	elágazás vége
eljárás vége
```
## Futási idő
- Általában O(nlog(n))
- Legrosszabb eset, ha fordítottan rendezett, vagy eleve rendezett tömbről van szó, ilyenkor O(n^2)