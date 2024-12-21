A bináris keresőfa egy összefüggő gráf, amiben minden csomópontnak maximum két gyereke van. Minden csúcs maximum egy éllel van összekötve, és csak egy gyökéreleme van. A gyerekekből a bal oldali mindig kisebb a csomóponttól, míg a jobboldali mindig nagyobb.
## Szerkezet
```plantuml
class FaElem<T, ahol T Összehasonlítható>{
	tart : T
	bal : FaElem<T>?
	jobb : FaElem<T>? 
	Létrehoz(tart : T, bal : FaElem<T>?, jobb : FaElem<T>?)
}

interface Halmaz<T> {
	Beszúr(érték : T)
	Eleme(érték : T) : logikai
	Töröl(érték : T)
	Bejár(művelet : eljárás<T>)
}
	
class FaHalmaz<T, ahol T összehasonlítható> implements Halmaz<T>{
	-gyökér : FaElem<T>
	+Létrehoz()
	+Felszabadít()
	+Beszúr(érték : T)
	-RészfábaBeszúr(p : FaElem<T>?, érték : T) : FaElem<T>?
	+Eleme(érték : T) : logikai
	-RészfaEleme(p : FaElem<T>?, érték : T) : logikai
	+Töröl(érték : T)
	-RészfábólTöröl(p : FaElem<T>?, r : FaElem<T>?) : FaElem<T>?
	-KétGyerekesTörlés(e : FaElem<T>?, r : FaElem<T>?) : FaElem<T>?
	+Bejár(művelet : eljárás<T>)
	-RészfaBejárásPreOrder(p: FaElem<T>?, művelet : eljárás<T>)
	-RészfaBejárásInOrder(p: FaElem<T>?, művelet : eljárás<T>)
	-RészfaBejárásPostOrder(p: FaElem<T>?, művelet : eljárás<T>)
}
```
## Algoritmusok
### Konstruktor
```pseudocode
eljárás FaHalmaz.Létrehoz()
	gyökér <- null
eljárás vége
```
### Destruktor
```pseudocode
eljárás FaHalmaz.Felszabadít()
eljárás vége
```
### Bejárás
```pseudocode
eljárás FaHalmaz.RészfaBejárásInOrder(p, művelet)
	ha p!=null akkor
		RészfaBejárásInOrder(p.bal, művelet)
		művelet(p.tart)
		RészfaBejárásInOrder(p.jobb, művelet)
	elágazás vége
eljárás vége
```

```pseudocode
eljárás FaHalmaz.RészfaBejárásPreOrder(p, művelet)
	ha p!=null akkor
		művelet(p.tart)
		RészfaBejárásPreOrder(p.bal, művelet)
		RészfaBejárásPreOrder(p.jobb, művelet)
	eljárás vége
eljárás vége
```

```pseudocode
eljárás FaHalmaz.RészfaBejárásPostOrder(p, művelet)
	ha p!=null akkor
		RészfabejárásPostOrder(p.bal, művelet)
		RészfabejárásPostOrder(p.jobb, művelet)
		művelet(p.tart)
	elágazás vége
eljárás vége
```
### Elem megléte
```pseudocode
függvény FaHalmaz.RészfaEleme(p, érték)
	ha p != null akkor
		ha p.tart < érték akkor
			RészfaEleme(p.bal, érték)
		különben ha p.tart > érték akkor
			RészfaEleme(p.jobb, érték)
		különben
			vissza igaz
		elágazás vége
	különben
		vissza hamis
	elágazás vége
függvény vége
```

```pseudocode
függvény FaHalmaz.Eleme(érték)
	vissza RészfaEleme(gyökér, érték)
függvény vége
```
### Beszúrás
```pseudocode
függvény RészfábaBeszúr(p, érték)
	ha p=null akkor
		új <- Létrehoz(FaElem<T> { 
				tart <- érték,
				bal <- null,
				jobb <- null 
			})
		vissza új
	különben
		ha p.tart > érték akkor
			p.bal <- RészfábaBeszúr(p.bal, érték)
		különben
			ha p.tart < érték akkor
				p.jobb <- RészfábaBeszúr(p.jobb, érték)
			elágazás vége
		elágazás vége
		vissza p
	elágazás vége
függvény vége
```

```pseudocode
függvény Beszúr(érték)
	gyökér <- RészfábaBeszúr(gyökér, érték)
függvény vége
```
### Törlés
```pseudocode
függvény FaHalmaz.RészfábólTöröl(p, érték)
	ha p!=null akkor
		ha p.tart > érték akkor
			p.bal <- RészfábólTöröl(p.bal, érték)
		különben
			ha p.tart < érték akkor
				p.jobb <- RészfábólTöröl(p.jobb, érték)
			különben
				ha p.bal=null akkor
					q <-p
					p <- p.jobb
					Felszabadít(q)
				különben
					ha p.jobb = null akkor
						q <- p
						p <- p.bal
						Felszabadít(q)
					különben
						p.bal <- KétGyerekesTörlés(p, p.bal)
					elágazás vége
				elágazás vége
			elágazás vége
		elágazás vége
		vissza p
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```

```pseudocode
függvény KétGyerekesTörlés(e, r)
	ha r.jobb != null akkor
		r.jobb <- KétGyerekesTörlés(e, r.jobb)
		vissza r
	különben
		e.tart <- r.tart
		q <- r
		r <- r.bal
		Felszabadít(q)
		vissza r
	elágazás vége
függvény vége
```

```pseudocode
eljárás FaHalmaz.Töröl(érték)
	gyökér <- RészfábólTöröl(gyökér, érték)
eljárás vége
```