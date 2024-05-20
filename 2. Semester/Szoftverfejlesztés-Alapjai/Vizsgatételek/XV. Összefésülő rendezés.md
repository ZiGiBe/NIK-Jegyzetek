# Összefésülő rendezés
## Bemenet
- x: T tömb
- bal: egész, x résztömb/tömb bal széle
- jobb: egész, x résztömb/tömb jobb széle
## Algoritmus
```pseudocode
eljárás ÖsszefésülőRendezés(x, bal, jobb)
	ha bal < jobb akkor
		center <- bal + jobb / 2
		ÖsszefésülőRendezés(x, bal, center)
		ÖsszefésülőRendezés(x, center + 1, jobb)
		Összefésül(x, bal, center, jobb)
	elágazás vége
eljárás vége
```
## Futási idő
$$
T(n) = n \cdot T(1) + O(n) + \dots + O(n) = n(1+\log_2{n}) = O(n\log{n})
$$
- O(n\*log(n))
# Összefésülés
## Bemenet
- x: T tömb
- bal: egész, x résztömb bal széle
- center: egész, x résztömb közepe
- jobb: egész, x résztömb jobb széle
## Algoritmus
```pseudocode
eljárás Összefésül(címszerint x, bal, center, jobb)
	n1 <- center - bal + 1
	y1 <- Létrehoz(T)[n1 + 1]
	ciklus i <- 1-től n1-ig
		y1[i] <- x[bal + i - 1]
	ciklus vége
	n2 <- jobb - center
	y2 <- Létrehoz(T)[n2+1]
	ciklus j<-1-től n2-ig
		y2[i] <- x[center + j]
	ciklus vége
	y1[n1 + 1] <- inf
	y2[n2 + 1] <- inf
	i <- 1
	j <- 1
	ciklus k<-bal-tól, jobb-ig
		ha y1[i] <= y2[j] akkor
			x[k] <- y1[i]
			i <- i + 1
		különben
			x[k] <- y2[j]
			j <- j + 1
		elágazás vége
	ciklus vége
eljárás vége
```