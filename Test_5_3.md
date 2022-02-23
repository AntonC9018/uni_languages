Fie gramatica independentă de context 

$ G=(V_N, V_T, P, S), \\\\
V_N=\\{ S,A, B,C,D,E \\}, \\\\ 
V_T=\\{ a, b, c, d, m\\}, \\\\
P=
\begin{cases}
S \rightarrow cBbc \\\\  
A \rightarrow Sdb  \\\\   
B \rightarrow bCC|DaB  \\\\
C \rightarrow abm|DaD  \\\\
E \rightarrow aCb  \\\\
D \rightarrow aD|Dm|Am  \\\\
\end{cases} $.

Construiţi gramatica independentă de context echivalentă eliminând simbolurile inutile.

~~De la $S$ putem ajunge la $B$, de la $B$ la $C$ și la $D$, de la $D$ la $A$. La $E$ nu putem ajunge, deci este inaccesibil~~.

Regulile inutile sunt de fapt acele reguli care mereu aduc la recursia infinită, de la care nu putem ajunge la o regulă care termină cu un set de terminale simplu.

Construim setul de reguli de la care putem ajunge la o regulă de formă $ R \rightarrow t $ unde $ t \in V_T^\star $.
Așa reguli sunt $C$ ($C \rightarrow abm$).
La $C$ putem ajunge de la $E$ ($E \rightarrow aCb$) și de la $B$ ($B \rightarrow bCC$).
La $B$ ajungem din $S$. La $S$ ajungem din $A$. La $A$ ajungem din $D$.
Astfel, din toate simbolurile putem ajunge la sfârșit.
Deci toate simbolurile sunt utile. 
