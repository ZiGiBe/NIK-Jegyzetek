#MOC #note 

## Descartes-szorzat:
$$
A \times B = \{ (a, b), a\in A, b \in B \}
$$
Az R halmazt relációnak nevezzük, ha:
$$
R \subseteq A_1 \times A_2 \times \dots \times A_n (n \geq 2)
$$
A reláció:
- Bináris, ha 
$$
R \subseteq A_1 \times A_2
$$
- Homogén, ha
$$
R \subseteq A \times A \times \dots \times A
$$
- Homogén bináris, ha
$$
R \subseteq A \times A
$$
## Reláció felírása:
$$
(A, B; R)
$$
- Indulási halmaz: A
- Érkezési halmaz: B
- Értelmezési tartomány: $$D_R = \{ a \in A |\exists b \in B, aRb \}$$
- Értékkészlet:$$R_R = \{ b\in B|\exists a \in A, aRb \}$$
## Reláció inverze
$$
(B, A;R^{-1})
$$
$$
R^{-1}=\{(b, a)\space|\space(a,b)\in R\}
$$
## Reláció kompozíciója

$$
(A,B;R) \space (C,D;S)
$$
$$
R\circ S
$$
$$
(C, B; R\circ S) \rightarrow (c,b) \space \exists a \in A \land B \space | \space
cSa  \space \land \space aRb
$$
### További relációk:
- [[Homogén bináris relációk]]
- [[Parciális rendezés]]