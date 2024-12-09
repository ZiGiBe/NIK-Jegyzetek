#note
## Függvénygörbe alatti terület
- Az \[\a, b\]\ intervallumon értelmezett nemnegatív, folytonos f függvény grafikonja alatti területet az f függvény \[\a, b\]\ intervallumon vett határozott integrálját értjük
$$
T = \int_{a}^{b}{f}
$$
## Függvénygörbe feletti terület
- Az \[\a, b\]\ intervallumon értelmezett folytonos f függvény csak negatív értékeket vesz fel, akkor integrálja negatív, de integráljának abszolút értéke ekkor a területe
$$
T = -\int_{a}^{b}{g} =\mid\int_{a}^{b}{g}\mid
$$
## Két függvénygörbe közé zárt terület
- Ha f és g \[a\, b\]\ intervallumon értelmezett valós-valós függvények és minden 
  x eleme \[\a, b\]\ esetén f(x) <= g(x) akkor normáltartománya:
$$
A = \{(x,y)\space | \space x \in[a,b], f(x) \leq y \leq g(x) \}
$$
- Ha f, g \[\a, b\]\ intervallumon értelmezett, ott integrálható valós-valós függvények, amelyekre minden x eleme \[\a, b\]\ esetén f(x)<=g(x) akkor a függvénygörbék által meghatározott normáltartomány területe:
$$
T = \int_{a}^{b}(g-f)
$$
## Forgástest térfogata
- \[\a, b\]\ intervallumon nemnegatív, folytonos f függvény grafikonjának x tengely körüli megforgatásával nyert forgástest térfogata
$$
V = \pi\int_{a}^{b}f^2(x)dx
$$
## Síkgörbe ívhossza
- Egy folytonos síkgörbe retifikálható, ha a görbéhez írt poligonok hosszának szuprémuma véges, ha egy görbe retifikálható akkor ívhozzán a szuprémumot értjük
- f függvényt folytonosan differenciálhatónak nevezzük I intervallumon, ha f differenciálható minden intervallumban szereplő x esetén és f deriváltfüggvénye is folytonos I intervallumon
- Ha f függvény \[\a, b\]\ intervallumon folytonosan differenciálható, akkor y=f(x), x\[\a, b\]\ görbe retifikálható és ívhossza:
$$
s = \int_{a}^{b}\sqrt{1+(f'(x))^2}dx
$$