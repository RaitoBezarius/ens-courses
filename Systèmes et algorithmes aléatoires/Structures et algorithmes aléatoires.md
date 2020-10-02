# Structures et algorithmes aléatoires

## Cours 2

### La méthode probabiliste

On veut prouver que $P(X \text{ vérifie }{\cal P})>0$, ce qui montrera que il existe un objet qui vérifie $\cal P$.

#### Application : nombres de Ramsey

$2^{n \choose 2}$ coloriages, on numérote les cliques de taille $k$ par $i$, et on note $A_i$ = $i$ est une clique monochrome.

Alors $P(A_i)=2^{- {k \choose 2}+1}$, et $P( inter A_i^C)>0$ donc il existe un coloriage sans clique monochrome si (condition sur k et n).

On en déduit un algorithme de construction d'un tel coloriage de type Monte-Carlo ( donc Las-Vegas comme on l'a vu ).

#### Méthode du premier moment ( argument de l'espérance )

On sait que $P(X\ge E(X)) > 0$ et $P(X \le E(X)) > 0$.

##### Application : MAXSAT

Soient $F$ une formule à $m$ clauses, $k_i$ le nombre de litéraux de la $i$-ème clause, et $k=\min_{i=1}^m k_i$.
Alors il existe une affectation des variables qui satisfait au moins $\sum_{i=1}^m (1-2^{-k_i}) \ge m(1-2^{-k})$ clauses.

Démo : on note $Y_j = 1_{\text{La j-ème clause est safisfaite}}$ et $Y = \sum Y_i$, puis on voit que $P(Y \ge E(Y)) > 0$, où $E(Y)$ est le minorant ci-dessus, donc il existe une affectation qui satisfait un tel nombre de clauses.

#### Méthode du second moment

