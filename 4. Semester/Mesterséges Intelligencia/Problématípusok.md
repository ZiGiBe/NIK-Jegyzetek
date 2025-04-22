## Keresési problémák
- Főbb kritériumok keresési problémáknál:
	- Teljesség (Megtalálja-e)
	- Optimalitás (Legjobb-e)
	- Időkomplexitás
	- Helykomplexitás
- Kereséstípusok:
	- Offline: Az állapotteret teljesen ismeri, ezzel dolgozik előre
	- Online: Csak a környezet felfedezése közben végez keresést
	- Nem megfigyelt környezet: Nincs közvetlen információ az aktuális állapotról
	- Részlegesen megfigyelt környezet: Csak némely részeit figyeli meg a környezetnek, predikciókkal, valószínűségekkel figyel meg.
### Szélességi keresés
- Szintenkénti vizsgálás
- Garantált megoldás
- $O(b^d)$ hely-, és időigény ($b$: ágszám, $d$: mélység)
### Mélységi keresés
- Ágankénti vizsgálat
- Nem garantál optimális megoldást
- $O(b^m)$ időigény ($m$: mélység)
- $O(bm)$ helyigény
### Heurisztikus keresés
#### A* keresés
- Költségfüggvényt használ, ami az adott állapottól a következő állapotnak költsége alapján folytatja útját.
- Költségfüggvénye: $f(n) = g(n) + h(n)$
	- $g(n)$: kezdőállapottól n-ig számított költség
	- $h(n)$ n-től célig becsült költség
- Teljes, optimális, ha nem becsül túl
- $O(b^d)$ időigény
#### Hegymászó probléma
- Megadott kezdőállapottal kezd
- Szomszédos állapotokat értékeli
- Legjobb szomszédos állapotba való átmenet
## Játékok
### Minimax algoritmus
- Feltételezi, hogy mindkettő játékos optimálisan játszik
- Befejező lépésben a hasznosságfüggvény eredményét dobja vissza
- Egyéb esetben a max a maximális, míg a min a minimális értéki állapotokat preferálja