#note
# Szerkezet
```plantuml
interface Szótar<K, T>{
	Beír(kulcs : K, érték : T)
	Kiolvas(kulcs : K) : T
	Töröl(kulcs : K)
}
```
# Megvalósítások
## Közvetlen címzés
### Elvek
- A kulcsoknak természetes számoknak kell lenniük
- Megadott tartományon belül kell maradnia a kulcsoknak
```plantuml
class KözvetlenSzótár<K, T; K egész>{
	-E : tömb<T>
	+Létrehoz()
	+Felszabadít()
	+Beír(kulcs : K, érték : T)
	+Kiolvas(kulcs : K) : T
	+Töröl(kulcs : K)
}
```
### Előnyök
- Minden művelet O(1) darab lépéssel megoldható
### Hátrányok
- Szigorú feltételek a kulcsokra
- Használhatóságát befolyásolja a lehetséges kulcsok számának és eltárolni kívánt elemek aránya
### Algoritmusok
#### Konstruktor
```pseudocode
eljárás Szótár.Létrehoz()
	E <- Létrehoz(tömb<T>|K|)
eljárás vége
```
#### Destruktor
```pseudocode
eljárás Szótár.Felszabadít()
	Felszabadít(E)
eljárás vége
```
#### Beírás
```pseudocode
eljárás Szótár.Beír(kulcs, érték)
	E[kulcs] <- érték
eljárás vége
```
#### Kiolvasás
```pseudocode
eljárás Szótár.Kiolvas(kulcs)
	ha E[kulcs] != null akkor
		vissza E[kulcs]
	különben
		hiba "Hibás kulcs"
	elágazás vége
eljárás vége
```
#### Törlés
```pseudocode
eljárás Szótár.Töröl(kulcs)
	E[kulcs] <- null
eljárás vége
```
## Túlcsordulási területtel
### Hasítás
- A közvetlen címzés egyik kiküszöbölése
- Lényege, hogy a kulcsokra legyen lehetőség transzformációt végezni, mielőtt címzésre használjuk
- Ilyenkor szükség van egy kulcshalmazra, indexhalmazra, illetve egy "hasítófüggvény"-re
- Kulcshalmaz: Egy tetszőleges típusú, méretű halmaz, ami a lehetséges kulcsokat tartalmazza.
- Indexhalmaz: Lehetséges indexeket tartalmazza
### Ideális hasítófüggvény
- Egyszerűen kiszámítható
- Kevés ütközést generáljon
- Egyenletesen ossza a kulcsokat szét
- Hasonló kulcsokat random, de egymástól távolra szórja
### Hasítófüggvény implementációk
#### Osztó módszer
- Általános alakja: $h(k) : k mod |I| + 1$
- A + 1 elhagyható, ha olyan nyelven programozunk, ahol 0-tól kezdődik az indexelés
#### Szorzó módszer
- Általános alak: $h(k) : Közepe_m(y \cdot k) + 1$
- y: tetszőleges konstans
- $Közepe_m$: Visszaadja az x szám tízes számrendszerbeli alakjának középső m számjegyét
### Kulcsütközés kezelése nélkül
#### Szerkezet
```plantuml
interface Szótár<K, T>{
	Beír(kulcs : K, érték : T)
	Kiolvas(kulcs : K) : T
	Töröl(kulcs : K)
}
class HasítóSzótár<K, T> implements Szótár{
	-E : tömb<T>
	-h : függvény<K->egész+>
	+Létrehoz(méret : egész+)
	+Felszabadít()
	+Beír(kulcs : K, érték : T)
	+Kiolvas(kulcs : K) : T
	+Töröl(kulcs : K)
}
```
#### Algoritmusok
##### Konstruktor
```pseudocode
eljárás Szótár.Létrehoz(méret)
	E <- Létrehoz(tömb<T>[méret])
eljárás vége
```
##### Destruktor
```pseudocode
eljárás Szótár.Felszabadít()
	Felszabadít(E)
eljárás vége
```
##### Beírás
```pseudocode
eljárás Szótár.Beír(kulcs, érték)
	E[h(kulcs)] <- érték
eljárás vége
```
##### Kiolvasás
```pseudocode
eljárás Szótár.Kiolvas(kulcs)
	ha E[h(kulcs)] != null akkor
		vissza E[h(kulcs)]
	különben
		hiba "Hibás kulcs"
	elágazás vége
eljárás vége
```
##### Törlés
```pseudocode
eljárás Szótár.Töröl(kulcs)
	E[h(kulcs)] <- null
eljárás vége
```
### Kulcsütközés kezelésével (hasító táblázattal)
#### Kulcsütközés
- Kulcsütközés alatt azt értjük, ha két különböző kulcshoz, a hasítófüggvény ugyanazt az indexet rendeli, azaz a tömb egy cellájában kettő elemit is kellene tárolni. Abban az esetben amíg a kulcshalmaz nagyobb, mint az indexhalmaz addig mindig kell számolni ütközéssel.
#### Szerkezet
```plantuml
class SzótárElem<K, T>{
	+kulcs : K
	+tart : T
	+Létrehoz(kulcs : K, tart : T)
}
interface Szótár<K, T>{
	Beír(kulcs : K, érték : T)
	Kiolvas(kulcs : K) : T
	Töröl(kulcs : K)
}
class HasítóSzótárTúlcsordulással<K, T> implements Szótár{
	-E : tömb<SzótárElem<K, T>>
	-h : függvény<K->egész+>
	-U : Lista<SzótárElem<K, T>
	+Létrehoz(méret : egész+)
	+Felszabadít()
	-KulcsKeres(kulcs : K) : SzótárElem<K, T>
	+Beír(kulcs : K, érték : T)
	+Kiolvas(kulcs : K) : T
	+Töröl(kulcs : K)
}
```
#### Algoritmusok
##### Kulcskeresés
###### Kulcskeresés elve
1. Először megnézzük, hogy a tömbben található-e a hasítófüggvény szerint elem.
2. Ha $\emptyset$, akkor nincs a tömbben a keresett kulcs
3. Ha nem, akkor lehet hogy nem a megfelelő kulcsú elem (kulcsütközés miatt), emiatt meg kell nézni, hogy a konkrét elem kulcsa megegyezik-e a keresett értékkel.
4. Ha azonos akkor ez a keresett kulcsú elem, így ez a visszatérési érték
5. Ha nem azonos, akkor a listában kell nézni, hogy van-e olyan kulcsú elem, amit megadtunk.
6. Ha találunk elemet, akkor az a visszatérési érték, különben $\emptyset$-et adunk vissza
```pseudocode
eljárás Szótár.KulcsKeres(kulcs)
	ha E[h(kulcs)] != null & E[h(kulcs)].kulcs = kulcs akkor
		vissza E[h(kulcs)]
	különben
		e <- null
		U.Bejár(x -> ha x.kulcs = kulcs akkor e <- x)
		vissza e
	elágazás vége
eljárás vége
```
##### Beírás
```pseudocode
eljárás Szótár.Beír(kulcs, érték)
	meglévő <- KulcsKeres(kulcs)
	ha meglévő != null akkor
		meglévő.tart <- érték
	különben
		új <- Létrehoz(SzótárElem<K, T>) { 
			kulcs <- kulcs, tart <- érték 
		}
		ha E[h(kulcs)] = null akkor
			E[h(kulcs)] <- új
		különben
			U.Hozzáfűz(új)
		elágazás vége
	elágazás vége
eljárás vége
```
##### Kiolvasás
```pseudocode
eljárás Szótár.Kiolvas(kulcs)
	meglévő <- KulcsKeres(kulcs)
	ha meglévő != null akkor
		vissza meglévő.tart
	különben
		hiba "Hibás index"
	elágazás vége
eljárás vége
```
##### Törlés
```pseudocode
eljárás Szótár.Töröl(kulcs)
	ha E[h(kulcs)] != null & E[h(kulcs)].kulcs = kulcs akkor
		Felszabadít(E[h(kulcs)])
		E[h(kulcs)] <- null
	különben
		e <- null
		U.Bejár(x -> ha x.kulcs = kulcs akkor e <- x)
		ha e != null akkor
			U.Töröl(e)
			Felszabadít(e)
		elágazás vége
	elágazás vége
eljárás vége
```
### Kulcsütközés kezelésével (Listával)
#### Nyílt címzés
- A lényege, hogy a beszúrandó elem kulcsához tartozó index terület foglalt a tömbben, akkor valamilyen szabályos módon lehessen új indexet keresni.
- A hasítófüggvény általános alakja így: $h(k,j) : (h(k) + j) mod |I| + 1$
- Előnye, hogy nem igényel kiegészítő listát, tárhelyet, stb. így erőforrásigénye kisebb, mint a hasító táblázatos megoldásé
- Hátránya, hogy kulcsütközést nem okozó elemeket se tudjuk konkrét helyükre berakni.
#### Szerkezet
```plantuml
class HasítóSzótárListával<K, T>{
	-E : tömb<Lista<SzótárElem>>
	-h : függvény<K->egész+>
	+Létrehoz(méret : egész+)
	+Felszabadít()
	+Beír(kulcs : K, érték : T)
	+Kiolvas(kulcs : K) : T
	+Töröl(kulcs : K)
}
```
#### Algoritmusok
##### Kulcs alapján való keresés
###### Elv
1. Megtaláljuk a keresett kulcsot tartalmazó elemet
2. j eléri a tömb méretét, ami azt jelenti, hogy nincs meg a keresett kulcs.
2. Találunk egy üres elemet, ami azt jelzi, hogy nincs benne a kulcs a tömbben.
```pseudocode
függvény Szótár.KulcsKeres(kulcs)
	j <- 0
	ciklus amíg j < E.méret & E[h(kulcs, j) != null] 
		& E[h(kulcs, j)].kulcs != kulcs
		j <- j + 1
	ciklus vége
	ha j < E.méret & E[h(kulcs, j)].kulcs != null akkor
		vissza E[h(kulcs, j)]
	kül
függvény vége
```