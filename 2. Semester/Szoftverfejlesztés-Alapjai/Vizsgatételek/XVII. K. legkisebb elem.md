# [[XVI. Quicksort#Szétválogatás támpont alapján|Szétválogatás]]
# K. legkisebb elem
## Bemenet
- x: T tömb
- bal: egész, x résztömbjének bal széle
- jobb: egész, x résztömbjének jobb széle
- k: egész, k-adik legkisebb elem amit keresünk
## Algoritmus
```pseudocode
függvény KLegkisebb(címszerint x, bal, jobb, k)
	ha bal = jobb akkor
		vissza x[bal]
	különben
		idx <- Szétválogat(x, bal, jobb)
		ha k < idx - bal + 1 akkor
			vissza KLegkisebb(x, bal, idx - 1, k)
		különben
			vissza KLegkisebb(x, idx + 1, jobb, k - (bal - idx + 1))
		elágazás vége
függvény vége
```
## Futási idő
$$
O(n) + O(\frac{n}{2}) + O(\frac{n}{4}) + \dots + O(1)
$$
- O(2n-1) = O(n)
- Legrosszabb eset, ha a szélre kerül mindig a támpont, ilyenkor O(n^2)
