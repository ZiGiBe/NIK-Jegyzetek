# Szabályok
1. Mindig fekete a gyökércsúcs
2. Minden piros csúcs minden gyereke fekete
3. Gyökérből levélbe vezető úton fekete csúcsok száma mindig azonos
# Forgatás
- Olyan műveletek, ami megváltoztatja a fa szerkezetét
- Működési elv
	- legyen $x$ ami körül forgatni szeretnénk, $y$ a baloldali gyereke
	- legyen $x$ jobboldali gyereke $y$ baloldali gyereke, ekkor a szülő hivatkozását átállítjuk $x$-re
	- $x$ elem helyére hozzuk fel $y$-t. Elsőként ilyenkor be kell állítani, hogy $y$ szülő hivatkozása egyezzen meg $x$-ével.
		- Ha $x$ gyökér, akkor a gyökért $y$-ra kell állítani
		- Ha $x$ baloldali gyerek, akkor szülője bal mutatóját kell állítani $y$-ra
		- Ha $x$ jobboldali gyerek, akkor szülője jobb mutatóját kell állítani $y$-ra
## Balra forgatás
```pseudocode
eljárás BalraForgatás(x)
	y <- x.jobb
	x.jobb <- y.bal
	ha y.bal != null akkor
		y.bal.szülő <- x
	elágazás vége
	y.szülő <- x.szülő
	ha x.szülő = null akkor
		gyökér <- y
	különben
		ha x = x.szülő.bal akkor
			x.szülő.bal <- y
		különben
			x.szülő.jobb <- y
		elágazás vége
	elágazás vége
	y.bal <- x
	x.szülő <- y
eljárás vége
```
## Jobbra forgatás
```pseudocode
eljárás JobbraForgatás(x)
	y <- x.bal
	x.bal <- y.jobb
	ha y.jobb != null akkor
		y.jobb.szülő <- x
	elágazás vége
	y.szülő <- x.szülő
	ha x.szülő = null akkor
		gyökér <- y
	különben
		ha x = x.szülő.jobb akkor
			x.szülő.jobb <- y
		különben
			x.szülő.bal <- y
		elágazás vége
	elágazás vége
	y.jobb <- x
	x.szülő <- y
eljárás vége
```
# Beszúrás
- Nem lehetséges rekurzívan beszúrni (nem ismeri a fát teljesen akkor)
- Gyökérbeszúrás kivételével mindig meghívjuk a javító függvényt.
### Beszúrás algoritmusa
```pseudocode
eljárás Beszúr(érték)
	ha gyökér = null akkor
		gyökér <- Létrehoz(PFFaElem<T>) {
			tart <- érték,
			szín <- fekete,
			szülő <- null
		}
	különben
		p <- gyökér
		ciklus amíg p != null
			q <- p
			ha p.tart > érték akkor
				p <- p.bal
				ha p = null akkor
					q.bal <- Létrehoz(PFFaElem<T>){
						tart <- érték,
						szín <- érték,
						szülő <- q
					}
					BeszúrásJavítás(q.bal)
				elágazás vége
			különben
				ha p.tart < érték akkor
					p <- p.jobb
					ha p = null akkor
						q.jobb <- Létrehoz(PFFaElem<T>){
							tart <- érték,
							szín <- piros,
							szülő <- q
						}
					BeszúrásJavítás(q.jobb)
				elágazás vége
			elágazás vége
		ciklus vége
	elágazás vége
eljárás vége
```
## Javítás
### Szabályok

- Ha a szülő fekete, nem kell javítani
- Ha a szülő piros, biztosan kell javítani
- Ekkor biztosan van egy fekete nagyszülő
### Piros nagybácsi esete
- Ha a nagybácsi piros, akkor csak átszínezéssel megoldható a probléma, ilyenkor a szülő és nagybácsi színe fekete, a nagyszülő piros.
- Ezután folytatni kell a nagyszülővel a javítást, amíg a gyökérig nem jutunk
- Gyökérhez jutáskor a gyökér színét át kell színezni feketére.
### Fekete, vagy null nagybácsi esete
- A szülő legyen fekete
- Nagyszülő piros
- Ilyenkor a nagybácsi irányába eggyel kevesebb a fekete csúcsok száma. Ilyenkor a nagyszülő körül kell balra forgatni.
- Amikor a szülő a nagyszülő jobboldali gyereke, a $p$ a szülő baloldali gyereke, ekkor $p$-t léptetjük szülőjére, jobbra forgatunk $p$ körül
- Amikor a szülő a nagyszülő baloldali gyereke, és $p$ a szülő baloldali gyereke, akkor az előzőhöz hasonlóan oldjuk meg csak felcseréljük az irányokat
### Algoritmus
```pseudocode
eljárás BeszúrásJavítás(p)
	ciklus amíg p.szülő != null & p.szülő.szín = piros
		ha p.szülő = p.szülő.szülő.bal akkor
			nagybácsi <- p.szülő.szülő.jobb
		különben
			nagybácsi <- p.szülő.szülő.bal
		elágazás vége
		ha nagybácsi != null & nagybácsi.szín = piros akkor
			p.szülő.szín <- fekete
			nagybácsi.szín <- fekete
			p.szülő.szülő.szín <- piros
			p <- p.szülő.szülő
		különben
			ha p.szülő = p.szülő.szülő.bal akkor
				ha p.szülő.jobb akkor
						p <- p.szülő
						ForgatásBalra(p)
				elágazás vége
			p.szülő.szín <- fekete
			p.szülő.szülő.szín <- piros
			ForgatásJobbra(p.szülő.szülő)
			különben
				ha p = p.szülő.bal akkor
					p <- p.szülő
					ForgatásJobbra(p)
				elágazás vége
				p.szülő.szín <- fekete
				p.szülő.szülő.szín <- piros
				ForgatásBalra(p.szülő.szülő)
			elágazás vége
		elágazás vége
	ciklus vége
	gyökér.szín <- fekete
eljárás vége
```