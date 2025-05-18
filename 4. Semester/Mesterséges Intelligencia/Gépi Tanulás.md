## Tanulás típusai
- Felügyelt tanulás
	- Bemenet-kimenet párok
	- Ez alapján leképzést készít a bemenetek és kimenetek között
- Felügyelet nélküli tanulás
	- Csak bemeneti adatokat lát az ügynök
	- Mintázatok, szerkezetek felismerése a cél
- Megerősítéses tanulás
	- Cselekvések végrehajtása
	- Jutalmat/Büntetés a környezettől a cselekvésekért
	- Optimális stratégia megtalálása a cél (Jutalom maximalizálásáért)
## Tanulási jellemzők
### Halmazok
Minden modellhez ajánlott alkalmazni tanulási-, és teszthalmazokat. A tanulási halmazok a modell betanítására használjuk, majd a tesztelési halmazokat arra, hogy megnézzük milyen teljesítményű a modell új adatokon.
### Torzítás
A torzítás a modell hajlama arra, hogy eltérjen az elvárt értékektől más halmazokon. Ez azért fontos, mivel előfordulhat, hogy a hipotézistér korlátozott és nem minden mintázatot tanul meg a modell emiatt. Ha a torzítás alacsony akkor a komplex mintázatok megtanulására képes lehet a modell, de a variancia nő emiatt. Magas torzítás pedig Underfitting-el jár.
### Under-, és Overfitting
#### Underfitting
- Nem tanulja meg megfelelően a mintázatokat adatok között
- Ennek fő oka az egyszerű hipotézistér
#### Overfitting
- Túlságosan illeszkedik a tanulási adatokra a modell, és nem általánosít jól új adaton.
- Oka a komplex hipotézistér
### Hiba
A tanulásnál a hiba három részből áll, ezek:
- Torzítás
- Variancia
- Zaj
Ebből a hiba kiszámítása: $Hiba = Torzítás^2 + Variancia + Zaj$
A célunk modellezésnél az egyensúly megtalálása a $Variancia$ és a $Zaj$ között.
## Felügyelt tanulás
- Főbb típusai:
	- Osztályozás
		- Véges halmazú kimenet esetén
	- Regresszió
		- Folytonos értékű kimenetek esetén
Felügyelt tanulás esetén adva van egy bemeneti $X$ tér, illetve egy kimeneti $Y$, ami egy ismeretlen $f$ függvényre épül. A tanulási algoritmus próbál egy közelítő modellt találni az ismeretlen függvényhez.