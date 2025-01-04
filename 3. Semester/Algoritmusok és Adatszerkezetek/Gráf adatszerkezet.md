#note
# Tárolási módok
- Gráfokat többféleképpen lehet tárolni, legfontosabbak:
	- Irányított/iránytalan
	- Súlyozott/súlytalan
	- Dinamikusan/Csúcsmátrixban/Szomszédsági lista
## Dinamikus tárolás
- A gráfot felvázolhatjuk úgy, hogy minden elemnek tetszőleges számú mutatója lehet, ami szomszédjaira hivatkozik.
- Ez akkor lehetséges, ha tudjuk minden csúcs között kiinduló élek maximális számát (akár tárolhatók listában).
- Csak irányított gráfokat lehetséges tárolni (mivel a referencia egyértelműen irányított)
- Tárolhatunk vele akár súlyozott gráfokat is, ha egy külön objektumként kezeljük.
## Csúcsmátrix
- A gráfot tárolhatjuk csúcsmátrixban is, ilyenkor el kell fogadni, hogy fix méretű a csúcsok száma.
- Egy kétdimenziós mátrix tárolja ilyenkor a gráfot, aminek sorai, oszlopai megegyezik a csúcsok számával.
- Irányítottság:
	- $M[i,j]$ meg kell egyezzen $M[j,i]$-vel, ha irányítatlan
	- Más esetben a gráf irányított
- Súly:
	- Ha $M$ csak igaz/hamis értéket tud tárolni, akkor súlytalan
	- Más esetben súlyozott
	- Súlyozott élek esetében figyelni kell, hogyan jelöljük két nem összekötött élt (pl.: a 0 nem mindig optimális, de például egy $NaN$ érték tud).
- Tárhely alapján nagyobb méretű gráfoknál jobban megéri választani
- Sebesség alapján akkor érdemes választani, ha nagyrészt élek létezését akarjuk vizsgálni
## Szomszédsági lista
- Minden csúcsnak adunk egy halmazt, ami tartalmazza szomszédjait.
- Meg lehet oldani fix mérettel, vagy dinamikus gráfként (lista, tömb, stb. alapú csúcstárolás).
- Tárhely szempontjából nem mindig effektív (nagy gráfok esetén)
- Sebesség szempontjából akkor érdemes választani, ha szomszédság alapján akarunk vizsgálgatni.
# Bejárások

## Szélességi bejárás
### Elv
- Elsőként a kiindulóponthoz legközelebbi csúcsokat dolgozza fel.
- Legközelebbi csúcsok után, az attól egy élnyi távolságra lévőket, majd így tovább
### Algoritmus
- Bemenet
	- $g$: a bejárandó gráf
	- $start$: a kiindulási csúcs
	- $művelet$: végrehajtandó művelet
- Kimenet
	- $F$: a bejárt csúcsok halmaza
```pseudocode
függvény SzélességiBejárás(g, start, művelet)
	S <- start
	F <- { start }
	ciklus amíg S != null
		k <- S.Sorból()
		művelet(k)
		g.Szomszédai(k).Bejár(x->{
			ha x nem eleme F akkor
				S.Sorba(x)
				F <- F U { x }	
		})
	ciklus vége
	vissza F
függvény vége
```
- Fontos, hogy ez az algoritmus csakis összefüggő gráfokat tud teljesen bejárni, ha minden csúcsot akarunk bejárni, akkor az összes csúcsra meg kell hívni egy ciklusban a bejárást.
## Mélységi bejárás
### Elv
- Elindul egy úton, majd addig halad mélyebbre, ameddig nincs olyan csúcsnál, amiről nem tud már továbblépni.
- Ezt addig folytatja, amíg el nem fogynak a feldolgozatlan szomszédok.
### Algoritmus
- Változók:
	- $k$: aktuálisan vizsgált csúcs
	- $g$: a gráf
	- $művelet$: a csúcsokon végrehajtandó művelet
	- $F$: a bejárt elemek halmaza
```pseudocode
eljárás MélységiBejárásRekurzió(g, k, cím F, művelet)
	F <- F U { k }
	művelet(k)
	g.Szomszédai(k).Bejár(x->{
		ha x nem eleme F akkor
			MélységiBejárásRekurzió(g, x, F, művelet)
		elágazás vége
	})
eljárás vége

eljárás MélységiBejárás(g, start, művelet)
	F <- {}
	MélységiBejárásRekurzió(g, start, F, művelet)
	vissza F
eljárás vége
```
# Topologikus rendezés
- Olyan sorba rendezés, amire igaz, hogy ha E-ben van egy él ($u$, $v$), akkor sorrendben $u$ meg kell előzze $v$-t
## Algoritmus
```pseudocode
eljárás TopologikusRekurzió(g, k, ref F, ref L)
	F <- F U { k }
	g.Szomszédai(k).Bejár(x-> {
		ha x nem eleme F akkor
			MélységiBejárásRekurzió(g, x, F, L)
		elágazás vége
	})
	L.Beszúr(1, k)
eljárás vége

függvény TopologikusRendezés(g)
	F <- {}
	L <- {}
	g.Csúcsok().Bejár(x->{
		ha x nem eleme F akkor
			TopologikusRekurzió(g, x, F, L)
		elágazás vége
	})
	vissza L
függvény vége
```
