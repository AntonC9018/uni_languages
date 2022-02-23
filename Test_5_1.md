Fie gramatica independentă de context 

$ G=(V_N, V_T, P, S), \\\\
V_N=\\{S,A,B,C,D\\}, \\\\ 
V_T=\\{ a, c, d \\}, \\\\
P=
\begin{cases}
S \rightarrow aABd \\\\  
S \rightarrow aBC  \\\\   
A \rightarrow Ac   \\\\
A \rightarrow aD \\\\
A \rightarrow \varepsilon  \\\\
C \rightarrow dA \\\\
B \rightarrow D  \\\\
B \rightarrow a  \\\\ 
D \rightarrow Da    \\\\
D \rightarrow a \\\\
D \rightarrow \varepsilon   \\\\
\end{cases} $.

Construiţi gramatica independentă de context echivalentă eliminând ε-producţiile.


$ D \rightarrow Da \xrightarrow{D \rightarrow \varepsilon} D \rightarrow a $

$ A \rightarrow aD \xrightarrow{D \rightarrow \varepsilon} A \rightarrow a $

$ B \rightarrow D \xrightarrow{D \rightarrow \varepsilon} B \rightarrow \epsilon $

$ S \rightarrow aABd \xrightarrow{A \rightarrow \varepsilon} S \rightarrow aBd $

$ A \rightarrow Ac \xrightarrow{A \rightarrow \varepsilon} A \rightarrow c $

$ C \rightarrow dA \xrightarrow{A \rightarrow \varepsilon} C \rightarrow d $

$ P^\prime=
\begin{cases}
S \rightarrow aABd|aBC|aBd \\\\  
A \rightarrow Ac|a|aD \\\\
C \rightarrow dA|d \\\\
B \rightarrow D|a|\varepsilon \\\\
D \rightarrow aa|a \\\\
\end{cases} $.

$ S \rightarrow aABd \xrightarrow{B \rightarrow \varepsilon} S \rightarrow aAd $

$ S \rightarrow aBC \xrightarrow{B \rightarrow \varepsilon} S \rightarrow aC $

$ S \rightarrow aBd \xrightarrow{B \rightarrow \varepsilon} S \rightarrow ad $

$ P^{\prime \prime}=
\begin{cases}
S \rightarrow aABd|aAd|aBC|aBd|aC|ad \\\\  
A \rightarrow Ac|a|aD \\\\
C \rightarrow dA|d \\\\
B \rightarrow D|a \\\\
D \rightarrow aa|a \\\\
\end{cases} $.