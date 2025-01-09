#note
A feljegyzéses módszer az [[Oszd meg és uralkodj]] módszer továbbfejlesztése abban, hogy a már kiszámolt értékeket nem futtatjuk le újra, így kevesebb lépésszámot elérve a programban.
## Elv
A feljegyzéses módszer annyiban különbözik, hogy minden esetben amikor teljesen új részeredményt számolunk, akkor feljegyezzük ezt egy tárolóban. Minden egyes számítás előtt megnézzük, hogy megtalálható-e ez a részmegoldás kiszámított értéke, ha igen, akkor azt adjuk vissza, így kevesebb számítást végezve.
## Hátizsák probléma algoritmusa
```pseudocode
függvény LegjobbRészmegoldás(t, h)
	ha (t = 0) v (h = 0) akkor
		vissza 0
	különben
		ha RészmegoldástKeres([t, h]) != null akkor
			vissza RészmegoldástKeres([t, h])
		különben
			Onem <- LegjobbRészmegoldás(t-1, h)
			ha h >= Wn akkor
				Oigen <- Pn + LegjobbRészmegoldás(t - 1, h - Wt)
				O <- max(Oigen, Onem)
			különben
				O <- Onem
			elágazás vége
			RészmegoldásTarolóbaÍr([t, h], O)
			vissza O
		elágazás vége
	elágazás vége
függvény vége
```
## Értékelés
- Jelentősen csökkenthető lépésszám
- Egyszerűen implementálható
- Csak akkor használható hatékonyan, ha sokszor kerül ugyanannak a részfeladat megoldására sor
- Magasabb tárhelyigény