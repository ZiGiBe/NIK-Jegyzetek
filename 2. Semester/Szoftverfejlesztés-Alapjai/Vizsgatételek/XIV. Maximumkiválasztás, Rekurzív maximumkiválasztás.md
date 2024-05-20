# [[I. Egyszerű programozási tételek#Maximumkiválasztás|Maximumkiválasztás]]
# Rekurzív maximumkiválasztás
## Bemenet
- x: T tömb
- bal: egész, a résztömb/tömb bal szélső indexe
- jobb: egész, a résztömb/tömb jobb szélső indexe
## Kimenet
- jobbmax, balmax, bal: egész, maximális értékek esetén a két résztömb nagyobbik eleme, jobb=bal esetén az adott elem indexe
## Algoritmus
```pseudocode
függvény FelezőMaximum(x, bal, jobb)
	ha bal = jobb akkor
		vissza bal
	különben
		center <- bal + jobb / 2
		balmax <- FelezőMaximum(x, bal, center)
		jobbmax <- FelezőMaximum(x, center + 1, jobb)
		ha x[balmax]>=x[jobbmax] akkor
			vissza balmax
		különben
			vissza jobbmax
		elágazás vége
függvény vége
```
## Futási idő
- Egy tömböt 1 elemű részhalmazokra n-szer lehet felosztani
$$
1 + 2 + \dots + \frac{n}{2} + n
$$
- Mértani sorozat: q=2
- Teljes futási idő:
$$
S(T_n) = \frac{2^{\log_2{n}+1}-1}{2-1} = 2n - 1
$$
- O(n)