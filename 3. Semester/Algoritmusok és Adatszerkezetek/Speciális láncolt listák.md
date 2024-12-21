#note
Láncolt lista, de menőbb
### Strázsaelem
- Láncolt listákban olyan elemek, amik az első, illetve utolsó valós adat után tárolunk.
- Üres tárolóban, mindig van két láncelem
- Olyan tartalmú elemeket tartalmaznak, amelyek biztosan nem értelmezhetőek a többi adatra
### Mutatott elem elé beszúrás
```pseudocode
eljárás StrázsaLánc.MutatottElemEléBeszúrás(p, érték)
	új <- Létrehoz(LáncElem<T>) { tart <- érték, köv <- p.köv }
	p.köv <- új
	p.tart <- érték
eljárás vége
```
### Mutatott elem törlése
```pseudocode
eljárás StrázsaLánc.MutatottElemTörlés(p)
	q <- p.köv
	p.tart <- q.tart
	p.köv <- q.köv
	Felszabadít(q)
eljárás vége
```
# Egyéb láncolások
## Kétirányú láncolás

### Szerkezet
```plantuml
class KétirányúLáncElem<T> {
	tart : T
	köv : LáncElem<T>?
	előző : LáncElem<T>?
}
```

- Előnye a visszafelé lépés lehetősége, így lehetséges hatékonyabb/gyorsabb megoldásokat írni.
- Hátránya a nagyobb helyfoglalás, illetve a módosító algoritmusok bonyolultabbak, mivel több referenciát is kell például állítani
## Ciklikus láncolás
- Hasonlóak az egyirányú láncoláshoz, de minden elem tárol egy-egy hivatkozást. Azaz a lánc utolsó eleme az első elemre hivatkozik