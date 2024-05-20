# Halmaztulajdonság vizsgálat
## Bemenet
- x: T tömb, növekvően rendezett
- n: x hossza
## Kimenet
- o: logikai, rendezettség
## Algoritmus
```pseudocode
függvény HalmazE(x, n)
	i <- 2
	ciklus amíg (i<=n) és (x[i]!=x[i-1])
		i <- i + 1
	ciklus vége
	o <- i > n
	vissza o
függvény vége
```
## Futási idő
- Összesen n-1 vizsgálat
- O(n)
# Tartalmazás
## Bemenet
- x: T halmaz
- n: egész, x hossza
- k: T, keresett érték
## Kimenet
- van: logikai
## Algoritmus
```pseudocode
függvény Tartalmazás(x, n, k)
	bal <- 1
	jobb <- n
	center <- bal + jobb / 2
	ciklus amíg (bal <= jobb) és (x[center]!=k)
		ha x[center] > k akkor
			jobb <- center - 1
		különben
			bal <- center + 1
		elágazás vége
		center <- bal + jobb / 2
	ciklus vége
	van <- bal <= jobb
	vissza van
függvény vége
```
## Futási idő
- 1 + log2(n) vizsgálat
- O(log(n))
# Részhalmaz
## Bemenet
- x1: T halmaz
- n1: egész, x1 hossza
- x2 T halmaz
- n2: egész, x2 hossza
## Kimenet
- o: logikai
## Algoritmus
```pseudocode
függvény Részhalmaz
	i <- 1
	j <- 1
	ciklus amíg (i <= n1) és (j <= n2) és (x1[i]>=x2[j])
		ha x1[i]=x2[j] akkor
			i <- i + 1
		elágazás vége
		j <- j + 1
	ciklus vége
	o <- i > n1
	vissza o
függvény vége
```
## Futási idő
- A ciklus mindig n2-ször fut le
- O(n2)