#note 
A B-fa egy olyan bináris keresőfa, amiben egy csomópont több elemet is tartalmazhat, és gyerekei száma lehet több, mint kettő.
## B-Fa tulajdonságai
- Rendezettség: Minden csúcsban igaz, hogy a tartalma rendezett
- Kiegyensúlyozott: Minden levél mélysége azonos
- Egyediség: két azonos tartalmú elem nem lehet
- Korlátos: minden csúcs maximálisan 2t-1 darab tartalma lehet, minden nemgyökér elemnek t-1 darab tartalma kell legyen (t a B-Fa minimális fokszáma, egy előre megadott mennyiség)
- A gyerekmutatók száma mindig tartalom száma + 1
## Egy elem szerkezete
```plantuml
class BFaElem<T, ahol T összehasonlítható>{
	n : egész+
	levél : logikai
	tart : tömb<T>[2t-1]
	gyerek : tömb<BFaElem<T>>[2t]
}
```
## Beszúrás
### Szabályok
- Ha a fa nem üres, meg kell vizsgálni, hogy a gyökérben hány érték található, ha ez a maximális elemszámmal egyenlő, akkor létrehoz egy új elemet, ami az új gyökér lesz, és szétvágja az aktuális gyökért úgy, hogy a középső érték az új csúcsba kerüljön. 
### Algoritmusok
```pseudocode
eljárás Beszúrás(érték)
	ha gyökér = null akkor
		gyökér <- Létrehoz(BFaElem<T>)
		gyökér.levél <- igaz
	különben
		ha gyökér.n = 2t-1 akkor
			p <- gyökér
			gyökér <- Létrehoz(BFaElem<T>)
			gyökér.levél <- hamis
			Szétvágás(p, gyökér)
		elágazás vége
	elágazás vége
	KeresÉsBeszúr(p, gyökér)
eljárás vége
```

```pseudocode
eljárás KeresÉsBeszúr(p, érték)
	ha p.levél akkor
		BeszúrásLevélbe(p, érték)
	különben
		gy <- CsúcsbanKeresés(p, érték)
		ha p.gyerek[gy].n = 2t-1 akkor
			Szétvágás(p.gyerek[gy], p)
			ha p.tart[gy] < érték akkor
				gy <- gy + 1
			elágazás vége
		elágazás vége
eljárás vége
```

```pseudocode
eljárás BeszúrásLevélbe(p, érték)
	i <- CsúcsbanKeresés(p, érték)
	ciklus j <- p.n-től i-ig
		p.tart[j+1] <- p.tart[j]
	ciklus vége
	p.tart[i] <- érték
	p.n <- p.n + 1
eljárás vége
```

```pseudocode
függvény CsúcsbanKeresés(p, érték)
	e <- 1
	v <- p.n
	ciklus
		k <- [(e + v) / 2]
		ha érték < p.tart[k] akkor
			v <- k - 1
		különben
			ha érték > p.tart[k] akkor
				e <- k + 1
			elágazás vége
		elágazás vége
	amíg e <= v & p.tart[k] != érték
	ha p.tart[k] >= érték akkor
		vissza k
	különben
		vissza k + 1
	elágazás vége
függvény vége
```

```pseudocode
eljárás Szétvágás(p, szülő)
	új <- Létrehoz(BFaElem)
	új.levél <- p.levél
	új.n <- t - 1
	ciklus i <- 1-től t-1-ig
		új.tart[i] <- p.tart[t + i]
	ciklus vége
	ha !új.levél akkor
		ciklus i <- 1-től t-ig
			új.gyerek[i] <- p.gyerek[t + i]
		ciklus vége
	elágazás vége
	p.n <- t - 1
	i <- 1
	ha szülő.n != 0 akkor
		ciklus amíg szülő.gyerek[i] != p
			i <- i + 1
		ciklus vége
		ciklus j <- szülő.n-től i-ig
			szülő.tart[j+1] <- szülő.tart[j]
		ciklus vége
		ciklus j <- szülő.n + 1-től (i + 1)-ig
			szülő.gyerek[j+1] <- szülő.gyerek[j]
		ciklus vége
	elágazás vége
	szülő.tart[i] <- p.tart[t]
	szülő.gyerek[i] <- p
	szülő.gyerek[i+1] <- új
	szülő.n <- szülő.n + 1
eljárás vége
```
## Törlés
### Szabályok
- Ha levélből törlünk, akkor ha van az aktuális levélnek t darab kulcsa, akkor egyszerűen törölhető
- Belső csúcsból:
	- ha x kulcshoz tartozó baloldali, vagy jobboldali gyereke legalább t darabot tartalmaz, akkor meg kell annak a részfának legnagyobb elemét keresni, ezt átmásolni x-hez, és rekurzívan folytatni kell ezt a törlést erre a legnagyobb elemre folytatni
	- Ha x bal- és jobboldalán t-nél kevesebb tartalom van, akkor a két gyerek összevonható x-el, az összevonás után az új kapott elemben töröljük x-et.
### Legalább t darab elem biztosítása
- Ha a baloldali testvérnek van legalább t darab tartalma, akkor a két testvérhez tartozó szülőbeli kulcsot levisszük a következő elem első kulcsaként, a baloldali testvér legnagyobb értékét felvisszük a szülőbe erre a helyre.
- Ha a jobboldali testvérnek van legalább t darab tartalma, akkor a két testvérhez tartozó szülőbeli kulcsot levisszük a következő elem utolsó kulcsaként, és a jobboldali testvér legkisebb elemét felvisszük a szülőbe.
- Ha mindkét testvérnek csak t-1 darab eleme van, akkor az egyik gyerek összevonható a következő elem csúcsával úgy, hogy levisszük a szülő rájuk hivatkozó kulcsát is.
### Algoritmusok
```pseudocode
eljárás Törlés(érték)
	KeresÉsTöröl(gyökér, érték)
	ha gyökér.n = 0 akkor
		gyökér <- gyökér.gyerek[1]
	elágazás vége
eljárás vége
```

```pseudocode
eljárás KeresÉsTöröl(p, érték)
	ha p = null akkor
		hiba "Nincs Elem"
	elágazás vége
	i <- CsúcsbanKeresés(p, érték)
	ha i <= p.n & p.tart[i] = érték akkor
		ha p.levél akkor
			ciklus j<-i-től p.n-1-ig
				p.tart[j] <- p.tart[j+1]
			ciklus vége
		p.n <- p.n - 1
	különben
		gyerekB <- p.gyerek[i-1]
		ha gyerekB.n >= t akkor
			p.tart[i] <- RészfaMax(gyerekB)
			KeresÉsTöröl(gyerekB, p.tart[i])
		különben
			gyerekJ <- p.gyerek[i+1]
			ha gyerekJ.n >= t akkor
				p.tart[i] <- RészfaMin(gyerekB)
				KeresÉsTöröl(gyerekB, p.tart[i])
			különben
				gyerekJ <- p.gyerek[i+1]
				ha gyerekJ.n >= t akkor
					p.tart[i] <- RészfaMin(gyerekJ)
					KeresÉsTöröl(gyerekJ, p.tart[i])
				különben
					ÖsszevonSzülőbőlLehoz(gyerekB, gyerekJ, p, i)
					KeresÉsTöröl(gyerekB, érték)
				elágazás vége
			elágazás vége
		elágazás vége
	különben
		tovább <- p.gyerek[i]
		testvérB <- (i > 1 ? p.gyerek[i-1] : null)
		testvérJ <- (i <= p.n ? p.gyerek[i+1] : null)
		ha tovább != null & tovább.n < t akkor
			ha testvérB != null & testvérB.n >= t akkor
				BalTestvérbőlÁthoz(tovább, testvérB, p, i)
			különben
				ha testvérJ != null & testvérJ.n >= t akkor
					JobbTestvérbőlÁthoz(tovább, testvérJ, p, i)
				különben
					ha testvérB != null akkor
						ÖsszevonSzülőbőlLehoz(testvérB, tovább, p, i-1)
						tovább <- testvérB
					különben
						ÖsszevonSzülőbőlLehoz(tovább, testvérJ, p, i)
					elágazás vége
				elágazás vége
			elágazás vége
		elágazás vége
	elágazás vége
eljárás vége
```

```pseudocode
eljárás BalTestvérbőlÁthoz(tovább, testvérB, szülő, i)
	tovább.n <- tovább.n + 1
	tovább.gyerek[tovább.n + 1] <- tovább.gyerek[tovább.n]
	ciklus j<- tovább.n-1-től 1-ig
		tovább.tart[j+1] <- tovább.tart[j]
		tovább.gyerek[j+1] <- tovább.gyerek[j]
	ciklus vége
	tovább.gyerek[1] <- testvérB.gyerek[testvérB.n + 1]
	tovább.tart[1] <- szülő.tart[i - 1]
	szülő.tart[i - 1] <- testvérB.tart[testvérB.n]
	testvérB.n <- testvérB.n - 1
eljárás vége
```

```pseudocode
eljárás JobbTestvérbőlÁthoz(tovább, testvérJ, szülő, i)
	tovább.n <- tovább.n + 1
	tovább.tart[tovább.n] <- szülő.tart[i]
	szülő.tart[i] <- testvérJ.tart[1]
	tovább.gyerek[tovább.n + 1] <- testvérJ.gyerek[1]
	ciklus j<-1-től testvérJ.n - 1-ig
		testvérJ.tart[j] <- testvérJ.tart[j + 1]
		testvérJ.gyerek[j] <- testvérJ.gyerek[j + 1]
	ciklus vége
	testvérJ.gyerek[testvérJ.n] <- testvérJ.gyerek[testvérJ.n + 1]
	testvérJ.n <- testvérJ.n - 1
eljárás vége
```

```pseudocode
eljárás ÖsszevonSzülőbőlLehoz(bal, jobb, szülő, i)
	bal.n <- bal.n + 1
	bal.tart[bal.n] <- szülő.tart[i]
	bal.gyerek[bal.n + 1] <- jobb.gyerek[1]
	ciklus j<-1-től jobb.n-ig
		bal.n <- bal.n+1
		bal.tart[bal.n] <- jobb.tart[j]
		bal.gyerek[bal.n] <- jobb.gyerek[j + 1]
	ciklus vége
	ciklus j <- i-től szülő.n - 1-ig
		szülő.tart[j] <- szülő.tart[j+1]
	ciklus vége
	ciklus j <- i + 1-től szülő.n-ig
		szülő.gyerek[j] <- szülő.gyerek[j + 1]
	ciklus vége
	szülő.n <- szülő.n - 1
eljárás vége
```