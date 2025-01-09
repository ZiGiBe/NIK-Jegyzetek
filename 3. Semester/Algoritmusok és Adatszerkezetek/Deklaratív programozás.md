#note 
# Alapelv
- Azt határozzuk meg, hogy mi a megoldandó feladat
- Megoldás módját a megoldó motor határozza meg
# Jellemzők
- Programkód csak feladatspecifikációt tartalmaz
	- Szabályrendszer
	- Feladat/kérdés specifikációja
- Részterületeket fed csak le
- Rövidebb egyszerű program
- Magas absztrakció
- Korlátos
- Nagyon hatékony
# Funkcionális programozás
- Kiemelt szerepe van a függvényeknek, és az azokkal végezhető műveleteknek
- Magas absztrakció
	- Függvényeket határozunk meg
	- A kiszámítandó végeredményt meghatározza
	- Végrehajtás sorrendje a motor által
- Felhasználás
	- Erősen korlátozott
	- Matematika
	- Optimalizálás
	- Ray-tracing
## Jellemzők
- Nincsenek változók, csak értékek
- Egyszer lehet csak értéket adni, amit később nem lehet változtatni
## Egyszerű függvények
- Bemeneti paraméterek alapján számol visszatérési értéket
- Nincs belső változó állapot ami befolyásolná ezt
- Függvények nem tudnak belső állapotot megváltoztatni
- Determinisztikus
- Nincs mellékhatása
- Párhuzamosan végrehajtható
- Egyszerűen tesztelhető
## Magasabb rendű függvények
- Tetszőleges visszatérési érték
- Akár másik függvény, mint visszatérési érték
- Egymásba építhetők
- Nincs kiértékelés
## Vezérlési szerkezetek
- Elágazás
- Ciklus
	- Nincsenek, mivel imperatív nyelveknél van
	- Helyette rekurzió
- Szekvencia
	- Nincsenek, mivel imperatív nyelveknél van
	- Helyette függvény kompozíció
## Speciális típusok
- Primitív
	- Számok
	- Logikai érték
	- Karakterek
	- Függvények
- Összetett
	- Tuple
	- Lista
	- Szöveg
## Párhuzamosítás
- Nincsenek változók
	- Nem időérzékeny
	- Nincs mellékhatás
- Nincsenek versenyhelyzetek
# Logikai programozás
- Hasonlít a funkcionális nyelvekhez
- Logikai értékkekkel dolgozik
- Célja a tudásreprezentáció
- Szakértői rendszerek alapja
## Szabályok
- Fő alkotóelemek a programban a szabályok
	- Felépítés: szabály neve + kifejezés
- Horn klózok
	- Klóz: diszjunkció (vagy)
	- Horn klóz: olyan klóy ahol maximum egy pozitív és tetszőleges darab negatív elem van
	  $x \lor \lnot a_1 \lor \lnot a_2 \lor \lnot a_3 \dots$
# Hibrid megvalósítások
## Változtathatatlan objektumok
- Osztályok final, tehát nem lehet leszármazottja
- Csak olvasható tulajdonságok
- Konstruktorban adott értékek
- Példák
	- Komplex szám osztály, Pont, stb.
	- String, DateTime
## Függvénymutatók
- Függvény kódja a memóriában, amit elérhető cím alapján
- Tároljuk használjuk
- Egyszerűen működik, hatékony
- Típusbiztonság nincs, és biztonsági problémák fordulhatnak elő
## OOP
- Függvénymutató helyett interfészek
- Függvény helyet megvalósító osztály/objektum
- Futásidőben változtatható objektum
- Objektum/művelet eltárolható
## Függvényreferenciák
- Metódus eltárolása változóban
- Ezen keresztül meghívható
- Jól használható
- Típusbiztonság