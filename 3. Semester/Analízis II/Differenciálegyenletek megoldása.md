- **n-edrendű differenciálegyenlet általános megoldása**:  Olyan függvény, amely deriváltjaival együtt kielégíti a differenciálegyenletet és pontosan n darab egymástól független paramétert tartalmaz
- **n-edrendű differenciálegyenlet partikuláris megoldása**: olyan függvény, ami deriváltjaival kielégíti a differenciálegyenletet és legfeljebb n-1 darab egymástól független paramétert tartalmaz
- **Integrálgörbe**: Az a grafikon, ami a differenciálegyenlet egy partikuláris megoldását ábrázolja a derékszögű koordinátarendszerben
## Szétválasztható változójú differenciálegyenletek
- Legyenek f, g adott egyváltozós valós függvények és y ismeretlen egyváltozós függvény, ekkor:
$$
y' = f(x)g(y)
$$
szétválasztható változójú differenciálegyenletnek nevezzük.
### Általános megoldás
$$
y' = f(x)g(y)
$$
$$
\frac{y'}{g(y)} = f(x)
$$
$$
\int{\frac{y'}{g(y)}dx} = \int{f(x)dx}
$$
$$
\int{\frac{1}{g(y)}dy} = \int{f(x)dx}
$$
$$
G(y)+C_1 = F(x)+C_2
$$
$$
G(y)=F(x) + C
$$


## Elsőrendű lineáris differenciálegyenletek
- Elsőrendű lineáris differenciálegyenlet: olyan differenciálegyenlet, ami elsőrendű, elsőfokú
- Általános alak:
$$
y' + g(x)y = h(x)
$$
- Homogén differenciálegyenlet: ha a h függvény 0
- Inhomogén differenciálegyenlet: ha a h függvény nem 0
- Állandó együtthatós differenciálegyenlet: ha a g függvény konstans
$$
\text{Állandó együtthatós fv.: } y' + ay = 0
$$
### Homogén differenciálegyenlet általános megoldása
$$
y' + g(x)y = 0
$$
$$
\frac{dy}{dx} = -g(x)y
$$
$$
\frac{dy}{y} = -g(x)dx
$$
$$
\int{\frac{dy}{y}} = -\int{{g(x)}dx}
$$
$$
\ln{|y|} = -G(x) + \ln{|C|} = \ln{e^{-G(x)}}+\ln{|C|} = \ln{|Ce^{-G(x)}|}
$$
$$
y = Ce^{-G(x)}
$$
### Homogén, állandó együtthatós differenciálegyenlet megoldása
$$
y = Ce^{-ax}
$$
## Elsőrendű lineáris differenciálegyenletek megoldása

- y'+g(x)y = h(x) elsőrendű differenciálegyenlet általános megoldását megkapjuk, ha a hozzárendelt homogén egyenlet megoldásához hozzáadjuk az eredeti egyenlet partikuláris megoldását
$$
y = y_h + y_p
$$

## Másodrendű lineáris differenciálegyenletek
- Olyan differenciálegyenlet, ami másodrendű és elsőfokú
- Általános alakja:
$$
y'' + p(x)y' + q(x)y = h(x)
$$
- Másodrendű, lineáris differenciálegyenlethez rendelt homogén egyenlet általános megoldásához hozzáadjuk az eredeti differenciálegyenlet partikuláris megoldását, akkor megkapjuk a differenciálegyenlet megoldását.
- Ha y1 és y2 megoldásai a másodrendű lineáris, homogén differenciálegyenletnek, akkor ezek lineáris kombinációja is megoldása a differenciálegyenletnek.
- y1 és y2 függvényeket lineárisan függetleneknek nevezzük, ha lineáris kombinációjuk 0.
- Ha y1 és y2 másodrendű lineáris homogén differenciálegyenlet két lineáris független megoldása, akkor a differenciálegyenlet minden megoldása előáll lineáris kombinációjukként.
- Az
  $$
ay''+by'+cy=0
	$$
	differenciálegyenlet karakterisztikus egyenletének a lambda szám gyöke, akkor az a függvény differenciálegyenlet partikuláris megoldása
$$
	\text{karakterisztikus egyenlet: }a\lambda^2+b\lambda+c=0
$$
$$
\text{Példa két valós gyökre: } \lambda^2-5\lambda+6=0 \rightarrow\lambda_1=2,\lambda_2=3
$$
$$
y = C_1e^{2x}+C_2e^{3x}
$$
- Ha a karakterisztikus egyenletnek egy valós gyöke van, akkor annak partikuláris megoldása:
$$
y_p = xe^{\lambda x} + e^{\lambda x}
$$
- Ha a karakterisztikus egyenletnek gyökei nem valósak, akkor a két gyök egymásnak komplex konjugáltja, és ekkor partikuláris megoldásai:
$$
y_1=cos\beta x, \space y_2 = sin\beta x
$$
- Két nem valós gyök esetén a differenciálegyenlet általános megoldása:
$$
\text{ha }\lambda=\pm\beta j\text{: }y = C_1\cos\beta x + C_2 \sin\beta x
$$
$$
\text{ha }\lambda = \alpha \pm \beta j\text{: } y = e^{\alpha x}(C_1\cos\beta x + C_2\sin\beta x)
$$