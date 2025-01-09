#note
## Neumann-számítógép
- CPU
	- Control Unit
	- ALU
	- Regiszterek
- Memória
- Perifériák:
	- Input
	- Output
	- Háttértár
	- Egyéb
## Az imperatív paradigma
- A program aktuális állapotát a memória aktuális tartalma határozza meg
- Ezt értékadó utasítások valósítják meg
- Ezeket megfelelő sorrendben kell végrehajtani, szükség van feltételes végrehajtásra, ugró utasításra
- Célja, hogy előállítson egy olyan utasításokból álló programot ami bármely megfelelő bemenettel az utasítások végrehajtásával addig változtatja a memória tartalmát, amíg az egy elvárt kimenetbe kerül át
## Memóriakezelés
### Típusok, változók
- Egyszerű típusok
	- logikai
	- egész
	- szám
	- szöveg
- Összetett típusok
	- Mérete az egyszerű a típusban szereplő egyszerű változók összege
	- Értékadáskor csak ugyanolyan típusú változónak lehet átadni.
	- Két azonos típus akkor egyenlő, ha minden mezőjük külön-külön egyenlő
### Memóriakezelési módszerek
#### Statikus memóriakezelés:
- A memória lefoglalásához nem kell külön utasítás, ezt a fordító fordítás során teszi meg.
- Memória felszabadítása automatikus
#### Dinamikus memóriakezelés:
- A lefoglalást és felszabadítást a programozónak kell elvégeznie (programnyelv függő!)
### Mutatók, referenciák
- Adat egy mások változón keresztüli elérése
- Speciális érték mutatók esetében, az üres, ami azt jelenti, hogy nincs érvényes adat a memóriacímen
## Paradigmák
- **Absztrakció**: részletek elrejtése
### Procedurális programozás
#### Gépi kód
- A processzor számára értelmezhető kód
- Alapesetben egyesével sorban hajtja vére az utasításokat
- Megtörési lehetőség:
	- Feltétel nélkül
	- Feltétellel: amennyiben teljesül, akkor a megadott címen folytatódik, egyébként a következő utasítással
- Előnyök:
	- Hatékonyság
- Hátrányok
	- Nehéz, időigényes
	- Nagy hibalehetőség
	- Nehéz karbantartás
#### Assembly
- Memonikok (Utasításkód szavakkal)
- Változók
- Címkék
- **Assembler**
	- Assembly <-> Gépi kódfordító
	- Memóriatartalom elhelyezés
	- Makrók, nyelvi elemek
- Sebességkritikus esetekben használható alternatíva
### Moduláris programozás
- Névterek, névütközések elkerülése érdekében
- Láthatósági szintek
- Interface: felület
- Implementáció: működés meghatározása
- Modulok
- Programtervez:
	- Kódújrafelhasználás
	- Absztrakció növelése (modulok belül rejtettek)
### Struktúrális programozás
- Alapelvei:
	- Szekvenciák
	- Feltételes elágazások
	- Feltételes ciklusok
- Goto eltávolítása
	- Háttérben megmarad
- Programtervezés:
	- Komplex probléma definiálása
	- Iteratív felbontása
	- Elemi lépések megvalósítása
## Objektum orientált elv
### Előnyök
- Rugalmasság
- Karbantarthatóság
- Párhuzamos fejlesztés
- Kódújrafelhasználás
### Hátrányok
- Több munkát igényelhet
### Absztrakció
- Kevésbé komplex
- Komplexitás elrejtése
	- Egységbezárás
		- Adatokat elrejtjük (biztonságos kód)
- Minden objektum önnálló egység
### Alapelemek
- Az OOP elvnek alapelemei az objektumok
- Minden objektum modellezés során azonosítható
- Ezek önálló életciklussal rendelkeznek
- Szolgáltatásokat nyújtanak
- Együttműködnek
### Osztályok
- Össze tudnak fogni
	- Ős adatokat, műveleteket örököl a leszármazott
	- A leszármazott ezt kiegészíthető új adattal, műveletekkel
	- Akár módosíthat is (metódus felülírása)
	- Felülírás történhet
		- Késői kötéssel (virtual, polimorfizmushoz)
		- Korai kötéssel
- Előnyök
	- Kódújrafelhasználás
	- Polimorfizmus
	- Hierarchia áttekinthető
### Interfészek, implementációk
- Interfész: Egy objektum “mit” csinál, meghatározza milyen feladatot old meg egy objektum/művelet
- Implementáció: Egy objektum “hogyan” csinálja, azaz a követelmenyéket adja meg
- Előnyök
	- Interfészek
		- Információ teljes elrejtése
		- Absztrakció legmagasabb
		- Függőségek csökkentése
		- Polimorfizmushoz jól alkalmazhatóak
		- 