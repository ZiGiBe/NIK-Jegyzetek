#note
A heurisztikus ("rátalásásos") módszer lényege, hogy az "optimális" megoldást véletlen rátalással adjuk meg. Fontos hogy a módszer egy részlegesen optimális megoldást ad meg, nem a legoptimálist.
## Általános algoritmus alakja
```pseudocode
függvény Heurisztikus()
	O <- Random(T)
	ciklus i<-1-től m-ig
		x <- Módosít(O)
		ha Jóság(O) > Jóság(x) akkor
			O <- x
		elágazás vége
	ciklus vége
függvény vége
```
## Módszer értékelése
- Nem determinisztikusak, azaz más más eredmények jöhetnek, mivel véletlenszerűen generált megoldásokat adunk.
- Gyorsabb számítás
- Menet közben is lehet találni egyre jobb eredményeket
- Nem ad pontos megoldást, ha mégis, akkor ebből a módszerből nem tudjuk meg
- Nem garantál minden futás jó eredményt
- Megkérdőjelezhető $m$ érték