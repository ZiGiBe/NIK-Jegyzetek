# N-dimenziós tér
- n-dimenziós tér:
$$
\mathbb{R}^n = \mathbb{R} \times \mathbb{R} \times \dots \times \mathbb{R}
$$
- n-dimenziós tér pontja:
$$
P(x_1, x_2, \dots, x_n)
$$
- n-dimenziós tér vektora: (P,Q) rendezett párok
- n-dimenziós vektor abszolút értéke:
$$
|\underline{a}| = \sqrt{\sum_{k=1}^n{a^2_k}}
$$
- n-dimenziós tér pontjainak távolsága:
$$
d(A,B) = |\underline{a} - \underline{b}| = \sqrt{\sum^n_{k=1}{(a_k-b_k)^2}}
$$
- n-dimenziós tér nyílt gömbje: azon P pontok halmaza, amelyre igaz, hogy (P, P0) < r teljesül
- n-dimenziós tér nyílt téglája:
$$
]a_1;b_1[ \times ]a_2;b_2[ \times \dots \times ]a_n;b_n[
$$
- n-dimenziós tér korlátos, ha létezik olyan gömb, vagy nyílt tégla, aminek H a részhalmaza
- n-dimenziós halmaz nyílt, ha minden pontnak van olyan környezete, ami része a H halmaznak.
- n-dimenziós térben a P pont a torlódási pontja, ha minden környezete tartalmaz P-től különböző H-beli pontot.
- H halmaz n-dimenzió térben zárt, ha minden torlódási pontját tartalmazza.
# Többváltozós függvények
- Többváltozós függvény:
$$
A\rightarrow \mathbb{R}, A \subseteq \mathbb{R}^n
$$
- Többváltozós függvény értelmezési tartománya:
$$
	H \subseteq \mathbb{R}^n
$$
- Lokális maximum: n-változós függvénynek lokális maximuma van P0 pontban, ha létezik P0-nak olyan K(P0) környezete, aminek minden P pontjára igaz hogy:
$$
f(P) \leq f(P_0)
$$
- Lokális minimum: n-változós függvénynek lokális minimuma van P0 pontban, ha létezik P0-nak olyan K(P0) környezete, aminek minden P pontjára igaz, hogy:
$$
f(P) \geq f(P_0)
$$
- Folytonosság: n-változós f valós függvény P0 helyen folytonos, ha:
$$
\forall\epsilon>0: |f(P)-f(P_0)| < \epsilon
$$
- n-változós függvény akkor és csak akkor folytonos P0 pontban, ha minden értelmezési tartományban lévő Pn pontsorozatban határértéke:
$$
\lim_{n\rightarrow\infty}P_n = P_0
$$
$$
\lim_{n\rightarrow\infty}f(P_n) = f(P_0)
$$
- Ha n-változós függvény értéke csak egyetlen változótól függ, és ebben a függvényben értelmezési tartományának minden pontjában folytonos, akkor az eredeti függvény is folytonos
## Folytonosság és műveletek
- ha f folytonos, akkor cf is folytonos
- ha f, g függvények folytonosak, akkor f+g, f-g, fg, és f/g (g(P0)!=0) is folytonosak
## Összetett függvények
$$
(\alpha\circ f)(P) = \alpha(f(P))
$$
- Ha n-változós f függvény és m-változós függvény is folytonos, akkor gf függvény is folytonos