- Minden algoritmusnak itt bemenete:
	- x: T Típusú tömb, ahol T összehasonlítható,
	- n: egész, x hossza
# Buborékrendezés
## Algoritmus
```pseudocode
eljárás BubbleSort(címszerint x, n)
	i <- n
	ciklus amíg (i>=2)
		idx <- 0
		ciklus i<-1-től i-1-ig
			ha x[j] > x[j+1] akkor
				x[j]<->x[j+1]
				idx <- j
			elágazás vége
		ciklus vége
		i <- idx
	ciklus vége
eljárás vége
```
## Futási idő
- n(n-1)/2 összehasonlítás
- Legjobb esetben n-1
- O(n^2)
# Minimumkiválasztásos Rendezés
## Algoritmus
```pseudocode
eljárás MinimumSort(címszerint x, n)
	ciklus i<-1-től n-1-ig
		min <- i
		ciklus j<-i+1-től n-ig
			ha x[min] > x[j] akkor
				min <- j
			elágazás vége
		ciklus vége	
		x[min]<->x[i]
	ciklus vége
eljárás vége
```
## Futási idő
- n(n-1)/2 összehasonlítás
- n-1 csere
- O(n^2)
# Beillesztéses Rendezés
## Algoritmus
```pseuducode
eljárás PasteSort(címszerint x, n)
	ciklus i<-2-től n-ig
		segéd <- x[i]
		j <- i - 1
		ciklus amíg (j>0) és (x[j]>segéd)
			x[j+1] <- x[j]
			j <- j- 1
		ciklus vége
		x[j+1] <- segéd
	ciklus vége
eljárás vége
```
## Futási idő
- Garantált cserék: 2(n-1)
- Összehasonlítások: n(n-1)/2
- Futási idő így: 2(n-1) + n(n-1)/2
- O(n^2)