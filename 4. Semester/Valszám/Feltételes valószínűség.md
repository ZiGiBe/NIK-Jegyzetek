**Feltételes valószínűség:** Ha $A$, $B$ egy kísérlettel kapcsolatos két tetszőleges esemény, és $P(B)>0$, akkor $A$ esemény $B$-re vonatkozó feltételes valószínűsége:
$$
P(A|B) = \frac{P(A\cdot B)}{P(B)}
$$
**Teljes valószínűség tétele:** Ha $B_1,B_2,\dots,B_n$ események teljes eseményrendszert alkotnak, és $B_i>0$, és $A$ egy tetszőleges esemény, akkor:
$$
P(A)=\sum^n_{i=1}P(A|B_i)\cdot P(B_i)
$$
**Bayes-tétel:** Ha $B_1, B_2, \dots, B_n$ események teljes eseményrendszert alkotnak, és $P(B_i)>0$, valamint $A$ egy tetszőleges esemény, akkor:
$$
P(B_k|A)=\frac{P(A|B_k)P(B_k)}{\sum^n_{i=1}P(A|B_i)P(B_i)}
$$