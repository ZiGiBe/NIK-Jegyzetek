# Sorozatszámítás
## Bemenet
- x: T típusú tömb
- n: egészérték, x tömb hossza
## Kimenet:
- érték: T, a sorozat
## Algortimus
```pseudocode
függvény Sorozat(x, n)
	érték <- érték_0
	ciklus i<-1-től n-ig
		érték <- érték + x[i]
	ciklus vége
	vissza érték
függvény vége
```
## Egyéb tudnivalók
- érték_0: Olyan érték, amely a T típuson értelmezett nullérték
- érték + x[i], olyan művelet, amely a T típuson értelmezett összegzés
## Futási idő
- n másolás összesen
- Egyenesen arányos O(n)-el
# Eldöntés
## Bemenet
- x: T tömb
- n: egészérték, x hossza
- P: Logikai függvény
## Kimenet
- van: logikai érték
## Algoritmus
```pseudocode
függvény Eldöntés(x, n, P)
	i <- 1
	ciklus amíg (i <= n) és !P(x[i])
		i <- i + 1
	ciklus vége
	van <- i <= n
	vissza van
függvény vége
```
## Futási idő
- Összesen n összehasonlítás
- O(n)
# Kiválasztás
## Bemenet
- x: T tömb,
- n: egészérték, x hossza
- P: logikai függvény
## Kimenet
- idx <- egészérték, a kiválasztott elem indexje a tömbben
## Algoritmus
```pseudocode
függvény Kiválasztás(x, n, P)
	i <- 1
	ciklus amíg !P(x[i])
		i <- i + 1
	ciklus vége
	idx <- i
	vissza idx
függvény vége
```
## Futási idő
- Legjobb esetben 1
- Legrosszabb esetben n összehasonlítás
- Átlagosan n/2
- O(n)
# Lineáris keresés
## Bemenet
- x: T tömb
- n: egészérték, x hossza
- P: logikai függvény
## Kimenet
- van: logikai érték
- idx: egészérték, a talált ember indexje
## Algoritmusok
```pseudocode
függvény LineárisKeresés(x, n, P)
	i <- 1
	ciklus amíg (i <= n) és !P(x[i])
		i <- i + 1
	ciklus vége
	van <- i <= n
	ha van akkor
		vissza(van, idx)
	különben
		vissza van
	elágazás vége
függvény vége
```
## Futási idő:
- Legjobb esetben 1
- Legrosszabb esetben n
- Átlagosan n/2
- O(n)
# Megszámlálás
## Bemenet
- x: T tömb
- n: egészérték, x hossza
- P: logikai függvény
## Kimenet
- db: egészérték, P tulajdonságú elemek száma
## Algoritmus
```pseudocode
függvény Megszámlálás(x, n, P)
	db <- 0
	ciklus i<-1-től n-ig
		ha P(x[i])
			db <- db + 1
		elágazás vége
	ciklus vége
	vissza db
függvény vége
```
## Futási idő
- n összehasonlítás
- O(n)
# Maximumkiválasztás
## Bemenet
- x: T tömb
- n: egészérték, x hossza
## Kimenet
- max: egészérték, a maximális elem indexe
## Algoritmus
```pseudocode
függvény Maximum(x, n)
	max <- 1
	ciklus i <- 2-től n-ig
		ha x[max] < x[i] akkor
			max <- i
		elágazás vége
	ciklus vége
	vissza max
függvény vége
```
## Futási idő
- n-1 vizsgálat
- O(n)