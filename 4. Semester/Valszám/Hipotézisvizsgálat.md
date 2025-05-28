## Statisztikai hipotézisek
**Statisztikai hipotézisnek:** Egy, vagy több valószínűségeloszlásra vonatkozó feltevés.
**Statisztikai próba:** Az az eljárás, aminek segítségével a hipotézis elfogadásáról, elutasításáról döntünk.
## Hipotézisvizsgálat menete (elméletben)
1. A feltételezett eloszlására, annak valamelyik paraméterére felállítunk egy $H_0$ hipotézist, ami mindig egyenlőség. Szükséges egy $H_1$ hipotézist is feltennünk, annak érdekében, hogy legyen egy alternatív hipotézisünk amit elfogadunk.
2. Próbafüggvény kiválasztása: A próbafüggvény egy olyan választott statisztikai függvény, amivel a $H_0$ fennállását vizsgáljuk.
3. Próbafüggvény eloszlásának meghatározása
4. Próba megbízhatósági, vagy szignifikanciaszintjének megadása
5. Kritikus, elutasítási tartomány kijelölése.
   Két részre szedjük a próbafüggvény értékkészletét, egy a Kritikus (elutasítási) tartomány, másik a az elfogadási tartomány. A tartományokat külön módszerekkel lehet kijelölni, ezek:
	1. Kétoldali próba $$
	   \begin{array}{l}
	   H_0: E(X)=m_0 \\
	   H_1: E(X)\neq m_0
	   \end{array}
	   $$
	2. Egyoldali próba
		1. Jobb oldali próba $$
		   \begin{array}{l}
		       H_0: E(X)\leq m_0 \\
		       H_1: E(X) > m_0
		   \end{array}		   $$
		2. Bal oldali próba $$
		   \begin{array}{ll}
		   H_0: E(X) \geq m_0 \\
		   H_1: E(X) < m_0
		   \end{array}
		   $$
6. $\hat{\alpha}_n$ próbafüggvény értékének meghatározása
7. Döntés annak függvényében, hogy a kritikus, vagy elfogadási tartományba esik a kiszámított érték.
## Hibafajták

|                    | $H_0$ igaz    | $H_0$ hamis    |
| ------------------ | ------------- | -------------- |
| $H_0$-t elfogadjuk | Jó döntés     | Másodfajú hiba |
| $H_1$-t elfogadjuk | Elsőfajú hiba | Jó döntés      |
