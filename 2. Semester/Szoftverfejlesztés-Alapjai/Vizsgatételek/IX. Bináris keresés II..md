## [[VIII. Bináris keresés I.#Rendezettség|Rendezettség]]
# Bináris keresés (Rekurzív)
## Bemenet
- x: T tömb
- bal: a résztömb/tömb bal oldali indexe
- jobb: a résztömb/tömb jobb oldali indexe
- k: T keresett érték
## Kimenet
- center: egész, indexe a keresett elemnek
## Algoritmus
```pseudocode
függvény BinárisKeresés(x, bal, jobb, k)
	ha bal > jobb akkor
		vissza 0
	különben
		center <- bal + jobb / 2
		ha x[center] > k akkor
			vissza BinárisKeresés(x, bal, center - 1, k)
		különben ha x[center] = k akkor
			vissza center
		különben
			vissza BinárisKeresés(x, center + 1, jobb, k)
		elágazás vége
függvény vége
```
## Futási idő
- Maximálisan 1 + log2(n) meghívás
- O(log(n))