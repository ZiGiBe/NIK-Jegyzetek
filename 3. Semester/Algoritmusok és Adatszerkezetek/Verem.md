Egy olyan adatszerkezet, ami LIFO (Last in, first out) alapján működik.
## Tömb alapú megvalósítás
### Szerkezet
```plantuml
interface Verem<T>{
	Üres: logikai { olvasható }
	Verembe(érték: T)
	Veremből(): T
	Felső(): T
}
class TömbVerem<T> implements Verem<T>{
	-E: tömb<T>
	-n: egész+
	+Üres: logikai { olvasható }

	+Létrehoz(méret: egész+)
	+Felszabadít()
	+Verembe(érték: T)
	+Veremből(): T
	+Felső(): T
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Verem.Létrehoz(méret)
	E <- Létrehoz(tömb<T>[méret])
	n <- 0
eljárás vége

Változók:
-E: tömb<T>, A verem tartalma
-n: egész+, indexelő
```
#### Felső
```pseudocode
függvény Verem.Felső()
	ha n > 0 akkor
		vissza E[n]
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége

Változók:
-E: tömb<T>, A verem tartalma
-n: egész+, indexelő

Kimenet: E[n], a verem legutoljára beszúrt eleme
```
#### Verembe
```pseudocode
eljárás Verem.Verembe(érték)
	ha n < E.méret akkor
		n <- n + 1
		E[n] <- érték
	különben
		hiba "Nincs hely"
eljárás vége

Változók:
-E: tömb<T>, A verem tartalma
-n: egész+, indexelő
```
#### Veremből
```pseudocode
függvény Verem.Veremből()
	ha n > 0 akkor
		érték <- E[n]
		n <- n - 1
		vissza érték
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége

Változók:
-E: tömb<T>, A verem tartalma
-n: egész+, indexelő
Kimenet:
-érték: T, a verem utolsó eleme
```

## Láncolás alapú megvalósítás
### Szerkezet
```plantuml
class LáncElem<T>{
	+tart: T
	+köv: LáncElem<T>?
	+Létrehoz(tart: T, köv: LáncElem<T>?)
}

interface Verem<T>{
	Üres: logikai
	Verembe(érték: T)
	Veremből(): T
	Felső(): T
}

class LáncVerem<T> implements Verem<T> {
	+Üres: logikai
	-fej : LáncElem<T>?
	+Létrehoz()
	+Felszabadít()
	+Verembe(érték: T)
	+Veremből() : T
	+Felső() : T
}
```
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Verem.Létrehoz()
	fej <- null
eljárás vége
```
#### Destruktor
```pseudocode
eljárás Felszabadít()
	fej <- null
eljárás vége
```
#### Verembe
```pseudocode
eljárás Verem.Verembe(érték)
	új <- Létrehoz(LáncElem<T>) { tart <- érték, köv <- fej }
	fej <- új
eljárás vége
```
#### Felső
```pseudocode
függvény Verem.Felső()
	ha fej != null akkor
		vissza fej.tart
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```
#### Veremből
```pseudocode
függvény Verem.Veremből()
	ha fej != null akkor
		érték <- fej.tart
		q <- fej
		fej <- fej.köv
		Felszabadít(q)
		vissza érték
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```