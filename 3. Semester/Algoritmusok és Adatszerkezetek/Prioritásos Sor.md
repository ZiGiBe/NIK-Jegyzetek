#note
## Rövid leírás
A prioritásos sor hasonlít a [[Sor]] adatszerkezetre, annyi különbséggel, hogy minden elemnek van egy "prioritása", ami alapján a Sorból() adja vissza az első elemet. Emiatt a beszúrás változik, mivel "rendezetten" kell beszúrni mindig, illetve kötelező emiatt egy "frissítő" eljárás is, ami alapján újra "átrakja" egy adott értéket a sor. A frissítő eljárást akkor használjuk, amikor feltételezhetjük, hogy a prioritás a sorban megváltozott (pl.: sorból való kivételkor)
## Szerkezet
```plantuml
interface PrioritásosSor<T, ahol T összehasonlítható>{
	Üres : logikai { olvasható }
	Sorba(érték : T)
	Sorból() : T
	Első() : T
	Frissít(érték : T)
}
class LáncoltPrioritásosSor<T, ahol T összehasonlítható> implements PrioritásosSor{
	-fej : LáncElem<T>?
	+Üres : logikai { olvasható }
	+Létrehoz()
	+Felszabadít()
	+Sorba(érték : T)
	+Sorból() : T
	+Első() : T
	+Frissít(érték : T)
}
```
## Algoritmusok
### [[Sor#Láncolás alapú implementáció#Konstruktor|Konstruktor]]
### [[Sor#Láncolás alapú implementáció#Destruktor|Destruktor]]
### [[Sor#Láncolás alapú implementáció#Sorból|Sorból]]
### [[Sor#Láncolás alapú implementáció#Első|Első]]
### Beszúrás
```pseudocode
eljárás PrioritásosSor.Sorba(érték : T)
	p <- fej
	e <- null
	ciklus amíg (p!=null) & (p.tart > érték)
		e <- p
		p <- p.köv
	ciklus vége
	ha e = null akkor
		új <- Létrehoz(LáncElem<T>) { tart <- érték, köv <- fej }
		fej <- új
	különben
		új <- Létrehoz(LáncElem<T>) { tart <- érték, köv <- fej }
		e.köv <- új
	elágazás vége
eljárás vége 
```
### Frissítés
```pseudocode
eljárás PrioritásosSor.Frissít(érték)
	Töröl(érték)
	Sorba(érték)
eljárás vége
```