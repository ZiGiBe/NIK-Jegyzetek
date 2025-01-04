#note
Egy olyan bináris fa, ami tömbben tárolható.
# Szabályok
1. A tömb 1. eleme a gyökér
2. Minden i. elemnek baloldali gyereke: 2i
3. Minden i. elemnek jobboldali gyereke: 2i+1
4. Rendezett, azaz egyes elemek gyerekei nem tartalmazhatnak nagyobb elemet
# Kupac tulajdonság fenntartása
- Lokális helyreállítás:
	1. A bal-, jobboldali gyerekek közül a nagyobbat kiválasztjuk
	2. Kicseréljük a gyökérrel
	3. A csere irányában nem biztos a rendezettség, erre a részfára rekurzívan karbantartunk
```pseudocode
eljárás Kupacol(i)
	b <- Bal(i)
	j <- Jobb(i)
	ha b <= n & E[b] > E[i] akkor
		max <- b
	különben
		max <- i
	elágazás vége
	ha j <= n & E[j] > E[max] akkor
		max <- j
	elágazás vége
	ha max != i akkor
		E[i] <-> E[max]
		Kupacol(max)
	elágazás vége
eljárás vége
```
# Kupac építése
- Egy olyan eljárás, ami bármely tömbből tud rendezett kupacot építeni
```pseudocode
eljárás KupacotÉpít()
	ciklus i <- [n/2]-től 1-ig visszafelés
		Kupacol(i)
	ciklus vége
eljárás vége
```
# Kupacrendezés
- Alapelv:
	1. Meglévő rendezetlen tömbben felépítjük a kupacot
	2. n->2-ig indítunk ciklust
	3. Tudjuk, hogy a gyökér maximális, ezért kicseréljük az utolsó elemmel, majd kupacolunk
```pseudocode
eljárás Rendez()
	KupacotÉpít()
	ciklus i<-n-től 2-ig visszafelé
		E[1] <-> E[i]
		n <- n-1
		Kupacol(1)
	ciklus vége
eljárás vége
```