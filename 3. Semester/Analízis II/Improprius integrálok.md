## Véges sok pontban nem értelmezett függvény improprius integrálja
- Ha f valós-valós függvény integrálható \[\a, b\]\ intervallumon, akkor értékét az intervallum véges sok pontjában megváltoztatva olyan g függvényt kapunk, ami ugyancsak integrálható
  \[\a, b\]\-n és megegyeznek
- Ha f valós-valós függvény x1 < x2 < ... < xn pontok kivételével értelmezett \[\a, b\]\ intervallum minden pontjában és ott korlátos, akkor tekintünk egy olyan függvényt ami  értelmezett
  \[\a, b\]\-n és x1 < x2 < ... < xn pontok kivételével a két függvény megegyezik. Ha ez a függvény integrálható \[\a, b], akkor integrálját f függvény \[\a, b] intervallumban vett improprius integráljának nevezzük
## Integrálás végtelen intervallumon
- f valós-valós függvény legyen értelmezett \[\a, végtelen\[\ intervallumon és integrálható minden \[\a, w] intervallumon, ahol a < w, ha
$$
\exists \lim_{\omega \rightarrow \infty}\int_{a}^{\omega}f
$$
és véges, akkor azt mondjuk hogy ez az improprius integrál konvergens és értéke ez a határérték, ha nem konvergens akkor az improprius integrál divergens.
- Ha egy c számra teljesül hogy improprius integráljai konvergensek akkor tetszőleges c* esetén is konvergensek integráljai és
$$
\int_{-\infty}^{c}{f} + \int_{c}^{\infty}{f} = \int_{-\infty}^{c^*}{f} + \int_{c^*}^{\infty}{f}
$$
## Nem korlátos függvények improprius integrálja
- Legyen f valós-valós függvény értelmezett \]\a, b\]\ intervallumon. Ha f nem korlátos az a pont jobb oldali környezetében, de integrálható minden \[\a + e, b] intervallumon,
  ahol 0 < e < b - a, továbbá létezik és véges:
$$
\int_{a}^{b}f = \lim_{\epsilon\rightarrow0^+}\int_{a+\epsilon}^{b}{f}
$$
akkor azt mondjuk hogy f \[\a, b] intervallumon impropriusan intergrálható
- Legyen f valós-valós függvény értelmezett ]a, b\[\ intervallumon és tegyük fel, hogy sem a jobb, sem b bal oldali környezetében nem korlátos, ha f impropriusan integrálható \[\a, c] és \[\c, b] intervallumokon, akkor impropriusan integrálható az \[\a, b] intervallumon és:
$$
\int_{a}^{b}f = \int_{a}^{c}f + \int_{c}^{b}f
$$

- Legyen f valós-valós függvény értelmezett \[\a, b] intervallumon, kivéve c-t. Ha f nem korlátos c pont környezetében, de impropriusan integrálható \[a, c\] és \[\c, b] intervallumon, akkor impropriusan integrálható \[\a, b]-n és értéke:
$$
\int_{a}^{b}{f} = \int_{a}^{c}{f} + \int_{c}^{b}{f}
$$
