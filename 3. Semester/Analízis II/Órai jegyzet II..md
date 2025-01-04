## n-dimenziós tér
- Az R^n = R x R x R x R x ... x R halmazt az n-dimenziós térnek nevezzük, ennek a térnek egy valós szám n-essel megadott eleme a tér pontja
- Jelölés: P(x1, x2, ..., xn)
## n-dimenziós vektor
- A tér pontjaiból alkotott (P, Q) rendezett párokat n-dimenziós vektornak nevezzük
- ### Vektorok összege:
$$
a + b = (a_1 + b_1, a_2 + b_2, \dots, a_n + b_n)
$$
- ### Vektorok skaláris szorzata:
$$
a\cdot b = (a_1b_1, a_2b_2, \dots, a_nb_n)
$$
- ### Vektor hossza:
$$
|a| = \sqrt{\sum_{k=1}^n{a^2_k}}
$$
- ### Két pont közötti távolság (Euklideszi távolság):
$$
d(A, B) = |a - b| = \sqrt{\sum_{k=1}^n{(a_k-b_k)^2}}
$$
- Távolság n-dimenziós térben:
	- d(A, B) >= 0
	- d(A, B) = 0, akkor A = B
	- d(A, B) = d(B, A)
	- d(A, C) <= d(A, B) + d(B, C)
## Topológiai tulajdonságok
### Nyílt gömb
- R^n térben egy tetszőleges P0 középpontú, r-sugarú nyílt gömbön azon P pontok halmazát értjük, ahol d(P, P0) < r teljesül
### Nyílt tégla
- Az ]a1;b1\[, ]a2; b2\[, ..., ]an; bn\[ véges hosszúságú nyílt intervallumok Descartes-féle szorzatát az n dimenziós tér nyílt téglájának nevezzük
### Környezet, korlátos halmaz
$$
H \subseteq R^n
$$
- halmaz korlátos, ha létezik olyan
$$
G \subseteq R^n
$$
	gömb, amelynek H részhalmaza
### Nyílt, zárt halmazok
- A H halmaz nyílt, ha minden P pontnak van olyan környezete amely része H halmaznak
- P pont torlódási pontja, ha P minden környezete tartalmaz P-től különböző H-beli pontot
- H halmaz zárt, ha minden torlódási pontját tartalmazza
- Nyílt halmaz komplementere zárt, zárt komplementere nyílt halmaz
## Többváltozós függvények
- A függvényt, ahol A n-dimenziós tér részhalmaza n-változós függvénynek nevezzük
- n-változós függvény értelmezési tartománya az a H halmaz, amelynek pontjaihoz a függvény értéket rendel