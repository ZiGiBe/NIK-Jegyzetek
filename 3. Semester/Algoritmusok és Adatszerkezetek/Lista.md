#note
*Infinite tömbök, yipee*
## Tömb alapú implementáció
### Szerkezet
```plantuml
interface Lista<T> {
	Elemszám : egész+ { olvasható }
	Kiolvas(index : egész+) : T
	Módosít(index : egész+, érték : T)
	Hozzáfűz(érték : T)
	Beszúr(index : egész+, érték : T)
	Töröl(érték : T)
	Bejár(művelet : eljárás<T>)
}
class TömbLista<T> implements Lista<T>{
	-E : tömb<T>
	-n : egész+
	+Elemszám : egész+ { olvasható }
	+Létrehoz(méret : egész+)
	+Felszabadít()
	+Kiolvas(index : egész+) : T
	+Hozzáfűz(érték : T)
	+Beszúr(index : egész+, érték : T)
	+Töröl(érték : T)
	+Bejár(művelet : eljárás<T>)
	-MéretNövel()
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Lista.Létrehoz(méret)
	E <- Létrehoz(tömb<T>[méret])
	n <- 0
eljárás vége
```
#### MéretNövel
```pseudocode
eljárás Lista.MéretNövel()
	E' <- E
	E <- Létrehoz(tömb<T>[E.méret*2])
	ciklus i<-1-től n-ig
		E[i] <- E'[i]
	ciklus vége
	Felszabadít(E')
eljárás vége
```
#### Beszúrás
```pseudocode
eljárás Lista.Beszúr(index, érték)
	ha index <= n + 1 akkor
		ha n = E.méret
			MéretNövel()
		elágazás vége
		n <- n + 1
		ciklus i <- n-től index + 1-ig visszafelé
			E[i] <- E[i-1]
		ciklus vége
		E[index] <- érték
	különben
		hiba "Hibás index"
	elágazás vége
eljárás vége
```
#### Hozzáfűzés
```pseudocode
eljárás Lista.Hozzáfűz(érték)
	Beszúr(n+1, érték)
eljárás vége
```
#### Kiolvasás
```pseudocode
függvény Lista.Kiolvas(index)
	ha index <= n akkor
		vissza E[index]
	különben
		hiba "Hibás index"
	elágazás vége
függvény vége
```
#### Módosítás
```pseudocode
eljárás Lista.Módosít(index, érték)
	ha index <= n akkor
		E[index] <- érték
	különben
		hiba "Hibás index"
	elágazás vége
eljárás vége
```
#### Törlés
```pseudocode
eljárás Lista.Töröl(érték)
	ciklus i<-1-től n-ig
		ha E[i] = érték akkor
			db <- db + 1
		különben
			E[i] <- E[i-db]
		elágazás vége
	ciklus vége
	n <- n - db
eljárás vége
```
#### Bejárás
```pseudocode
eljárás Lista.Bejár(művelet)
	ciklus i<-1-től n-ig
		művelet(E[i])
	ciklus vége
eljárás vége
```
## Lánc alapú implementáció
### Szerkezet
```plantuml
class LáncElem<T>{
	+tart: T
	+köv: LáncElem<T>?
	+Létrehoz(tart: T, köv: LáncElem<T>?)
}
interface Lista<T> {
	Elemszám : egész+ { olvasható }
	Kiolvas(index : egész+) : T
	Módosít(index : egész+, érték : T)
	Hozzáfűz(érték : T)
	Beszúr(index : egész+, érték : T)
	Töröl(érték : T)
	Bejár(művelet : eljárás<T>)
}
class LáncoltLista<T> implements Lista<T>{
	+Elemszám : egész+ { olvasható }
	-fej : LáncElem<T>?
	+Létrehoz()
	+Felszabadít()
	+Kiolvas(index : egész+) : T
	+Módosít(index : egész+, érték : T)
	+Hozzáfűz(érték : T)
	+Beszúr(index : egész+, érték : T)
	+Töröl(érték : T)
	+Bejár(művelet : eljárás<T>)
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Lista.Létrehoz()
	fej <- null
eljárás vége
```
#### Destruktor
```pseudocode
eljárás Lista.Felszabadít()
	ciklus amíg fej != null
		p <- fej
		fej <- fej.köv
		Felszabadít(p)
	ciklus vége
eljárás vége
```
#### Hozzáfűzés
```pseudocode
eljárás Lista.Hozzáfűz(érték)
	új <- Létrehoz(LáncElem<T> { tart <- érték, köv <- null })
	ha fej = null akkor
		fej <- új
	különben
		p <- fej
		ciklus amíg p.köv != null
			p <- p.köv
		ciklus vége
		p.köv <- új
	elágazás vége
eljárás vége
```
#### Beszúrás
```pseudocode
eljárás Lista.Beszúr(index, érték)
	ha (fej = null V index = 1) akkor
		új <- Létrehoz(LáncElem<T>{ tart <- érték, köv <- fej })
		fej <- új
	különben
		p <- fej
		i <- 2
		ciklus amíg (p.köv != null) & (i < index)
			p <- p.köv
			i <- i + 1
		ciklus vége
		ha i <= index akkor
			új <- Létrehoz(LáncElem<T>{ tart <- érték, köv <- p.köv })
			p.köv <- új
		különben
			hiba "Hibás index"
		elágazás vége
eljárás vége
```
#### Módosítás
```pseudocode
eljárás Lista.Módosít(index, érték)
	p <- fej
	i <- 1
	ciklus amíg (p!=null) & (i < index)
		p <- p.köv
		i <- i + 1
	ciklus vége
	ha p != null akkor
		p.tart <- érték
	különben
		hiba "Hibás index"
	elágazás vége
eljárás vége
```
#### Törlés
```pseudocode
eljárás Lista.Töröl(érték)
	p <- fej
	e <- null
	ciklus
		ciklus amíg (p!=null) & (p.tart != érték)
			e <- p
			p <- p.köv
		ciklus vége
		ha p != null akkor
			q <- p.köv
			ha e = null akkor
				fej <- q
			különben
				e.köv <- q
			elágazás vége
			Felszabadít(p)
			p <- q
		elágazás vége
	amíg p != null
eljárás vége
```
#### Bejárás
```pseudocode
eljárás Lista.Bejár(művelet)
	p <- fej
	ciklus amíg p != null
		művelet(p.tart)
		p <- p.köv
	ciklus vége
eljárás vége
```
#### Kiolvasás
```pseudocode
függvény Lista.Kiolvas(index)
	p <- fej
	i <- 1
	ciklus amíg (p!=null) & (i < index)
		p <- p.köv
		i <- i + 1
	ciklus vége
	ha p != null akkor
		vissza p.tart
	különben
		hiba "Hibás index"
	elágazás vége
függvény vége
```