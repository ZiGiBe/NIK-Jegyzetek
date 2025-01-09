#note
Olyan algoritmusok, amelyek feladatok megoldása közben a részprobléma megoldásának aktuálisan legjobb részmegoldást választják.
A problémák szűk körénél ad csak teljesen optimális megoldást.
## Hátizsák probléma mohó algoritmussal
A hátizsák problémát sajnos "szimplán" nem lehet megoldani mohó algoritmussal. Viszont van lehetőség olyan szabályrendszer létrehozására, amivel egy "optimális" megoldást találunk.
Néhány Szabályrendszer:
1. A bepakolandó elemeket rendezhetjük súly szerint növekvő sorrendben
2. A bepakolandó elemeket rendezhetjük érték szerint csökkenő sorrendben
3. A bepakolandó elemeket rendezhetjük súly/érték arány szerint
### Algoritmus súly szerint
```pseudocode
függvény MohóHátizsák()
	TárgyakRendezése()
	O <- [hamis, hamis, hamis, ..., hamis]
	i <- 1
	ciklus amíg (Összsúly(O) <= Wmax) & (i <= n)
		ha Összsúly(O) + Wi <= Wmax akkor
			O[i] <- igaz
		elágazás vége
		i <- i + 1
	ciklus vége
	vissza Összérték(O)
függvény vége
```
# Értékelés
- Erőforrásigénye alacsony
- Relatív jól használható megoldást ad vissza, ha nem optimálist
- Csak szűk körben használható