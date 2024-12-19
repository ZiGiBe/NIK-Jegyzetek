Egy olyan adatszerkezet, ami FIFO (First in, First Out) alapján működik
## Tömb alapú implementáció
### Szerkezet
```plantuml
interface Sor<T>{
	Üres : logikai
	Sorba(érték : T)
	Sorból() : T
	Első() : T
}
class TömbSor<T> implements Sor<T>{
	+Üres : logikai
	-E : tömb<T>
	-e : egész+
	-u : egész+
	-n : egész+
	+Létrehoz(méret: egész+)
	+Felszabadít()
	+Sorba(érték : T)
	+Sorból() : T
	+Első() : T
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Sor.Létrehoz(méret)
	E <- Létrehoz(tömb<T>[méret])
	n <- 0
	e <- 0
	u <- 0
eljárás vége
```
#### Sorba
```pseudocode
eljárás Sor.Sorba(érték)
	ha n < E.méret akkor
		n <- n + 1
		u <- (u mod E.méret) + 1
		E[u] <- érték
	különben
		Hiba "Nincs hely"
	elágazás vége
eljárás vége
```
#### Első
```pseudocode
függvény Sor.Első()
	ha n > 0 akkor
		vissza E[(e mod E.méret) + 1]
	különben
		vissza "Nincs elem"
	elágazás vége
függvény vége
```
#### Sorból
```pseudocode
függvény Sor.Sorból()
	ha n > 0 akkor
		n <- n - 1
		e <- (e mod E.méret) + 1
		érték <- E[e]
		vissza érték
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```
## Láncolás alapú implementáció
### Szerkezet
```plantuml
interface Sor<T>{
	Üres : logikai { olvasható }
	Első() : T
	Sorba(érték : T)
	Sorból() : T
}
class LáncoltSor<T> implements Sor<T> {
	+Üres: logikai { olvasható }
	-fej: LáncElem<T>?
	-vége: LáncElem<T>?
	+Létrehoz()
	+Felszabadít()
	+Sorba(érték : T)
	+Sorból()
	+Első()
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Sor.Létrehoz()
	fej <- null
	vége <- null
eljárás vége
```
#### Destruktor
```pseudocode
eljárás Sor.Felszabadít()
	ciklus amíg fej.köv != null
		q <- fej
		fej <- fej.köv
		Felszabadít(q)
	ciklus vége
eljárás vége
```
#### Első
```pseudocode
függvény Sor.Első()
	ha fej != null akkor
		vissza fej.tart
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```
#### Sorból
```pseudocode
függvény Sor.Sorból()
	ha fej != null akkor
		érték <- fej.tart
		q <- fej
		fej <- fej.köv
		ha fej = null akkor
			vége <- null
		elágazás vége
		Felszabadít(q)
		vissza érték
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```
#### Sorba
```pseudocode
eljárás Sor.Sorba(érték)
	új <- Létrehoz(LáncElem<t>) { tart <- érték, köv <- null }
	ha vége != null akkor
		vége.köv <- új
	különben
		fej <- új
	elágazás vége
	vége <- új
eljárás vége
```