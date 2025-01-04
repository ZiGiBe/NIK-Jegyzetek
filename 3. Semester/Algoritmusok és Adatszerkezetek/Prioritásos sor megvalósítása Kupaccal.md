#note
# [[Prioritásos Sor#Rövid leírás|Tudnivalók]]
# Szerkezet
```plantuml
interface PrioritásosSor<T, ahol T összehasonlítható>{
	Üres : logikai { olvasható }
	Sorba(érték : T)
	Sorból() : T
	Frissít(érték : T)
}

class Kupac<T, ahol T összehasonlítható>{
	#E : tömb<T>
	#n : egész+
	+Bal(i : egész+) : egész+
	+Jobb(i : egész+) : egész+
	+Szülő(i : egész+) : egész+
	#Kupacol(i : egész)
	#KupacotÉpít()
}

class KupacPrioritásosSor<T, ahol T összehasonlítható> implements PrioritásosSor{
	+Üres : logikai { olvasható }
	+Létrehoz(méret : egész+)
	+Felszabadít()
	-KulcsotFelvisz(i : egész+)
	+Sorba(érték : T)
	+Sorból() : T
	+Első() : T
	+Frissít(érték : T)
}
Kupac <|-- KupacPrioritásosSor
```
# Algoritmusok
## [[Kupac|Kupac műveletek algoritmusai]]
## Kulcsfelvitel
```pseudocode
eljárás KulcsotFelvisz(i)
	sz <- Szülő(i)
	ha sz >= 1 & E[sz] < E[i] akkor
		E[sz] <-> E[i]
		KulcsotFelvisz(sz)
eljárás vége
```
## Sorba
```pseudocode
eljárás Sorba(érték)
	ha n < E.méret akkor
		n <- n + 1
		E[n] <- érték
		KulcsotFelvisz(n)
	különben
		hiba "Nincs hely"
	elágazás vége
eljárás vége
```
## Sorból
```pseudocode
függvény Sorból()
	ha !Üres akkor
		max <- E[1]
		E[1] <- E[n]
		n <- n - 1
		Kupacol(1)
		vissza max
	különben
		hiba "Nincs elem"
	elágazás vége
függvény vége
```
## Frissítés
```pseudocode
eljárás Frissít(érték)
	i <- 1
	ciklus amíg i <= n & E[i] != érték
		i <- i + 1
	ciklus vége
	ha i <= n akkor
		KulcsotFelvisz(i)
		Kupacol(i)
	különben
		hiba "Nincs elem"
	elágazás vége
eljárás vége
```