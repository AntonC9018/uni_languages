
$ G=(V_N, V_T, P, S), \\\\
V_N=\\{S,A,B,C\\}, \\\\ 
V_T=\\{ a,b, c, d\\}, \\\\
P=
\begin{cases}
S \rightarrow aB|ab \\\\  
A \rightarrow Bab|Aa|Aaa  \\\\   
B \rightarrow AcBC|ba|d  \\\\
C \rightarrow AC|CaBb|AB  \\\\
\end{cases} $.

Construiţi gramatica independentă de context echivalentă eliminând recursia stângă (două metode).

Primii candidați: $ A \rightarrow Aa|Aaa $.
Putem imediate elimina regula $ A \rightarrow Aaa $ deoarece ea se deduce din $ A \rightarrow Aa $.

$ A \rightarrow Aa $

Adaugăm o regulă nouă $ X_A \rightarrow a | a X_A $, iar $ A $ o transformăm în $ A \rightarrow Bab X_A | Bab $.


$ C \rightarrow CaBb $

$ X_C \rightarrow aBb | aBb X_C $, $ C \rightarrow AC X_C | AC | AB X_C | AB $

$ P=
\begin{cases}
S \rightarrow aB|ab \\\\  
A \rightarrow Bab X_A | Bab  \\\\ 
X_A \rightarrow a | a X_A  \\\\  
B \rightarrow AcBC|ba|d  \\\\
C \rightarrow AC X_C | AC | AB X_C | AB  \\\\
X_C \rightarrow aBb | aBb X_C \\\\
\end{cases} $.


Cealalta variantă adaugă regula cu $ \varepsilon $.

$ P=
\begin{cases}
S \rightarrow aB|ab \\\\  
A \rightarrow Bab X_A  \\\\ 
X_A \rightarrow a X_A | \varepsilon  \\\\  
B \rightarrow AcBC|ba|d  \\\\
C \rightarrow AC X_C | AB X_C |   \\\\
X_C \rightarrow aBb X_C | \varepsilon \\\\
\end{cases} $.