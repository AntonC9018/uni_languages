Fie gramatica independentă de context 

$ G=(V_N, V_T, P, S), \\\\
V_N=\\{S,A,L,M\\}, \\\\ 
V_T=\\{ a,b,d,f\\}, \\\\
P=
\begin{cases}
S \rightarrow LAM \\\\  
A \rightarrow dLf  \\\\   
L \rightarrow bab|b|bA   \\\\
M \rightarrow aaM|aa  \\\\
\end{cases} $.

Construiţi gramatica independentă de context echivalentă eliminând factorizarea.


$A$ mereu începe cu $d$. Putem înlinia acest $d$ peste tot. (acest $d$ și înseamnă factorizarea).

$ A \rightarrow d A^\prime $

$ A^\prime \rightarrow Lf $

$ S \rightarrow LAM \xrightarrow{A \rightarrow d A^\prime} S \rightarrow Ld A^\prime M $

$ L \rightarrow bA \xrightarrow{A \rightarrow d A^\prime} S \rightarrow bd A^\prime $

$P^{\prime}=
\begin{cases}
S \rightarrow Ld A^\prime M \\\\  
A^\prime \rightarrow Lf  \\\\   
L \rightarrow bab|b|bd A^\prime   \\\\
M \rightarrow aaM|aa  \\\\
\end{cases} $.

$ L \rightarrow b L^\prime $

$ L^\prime \rightarrow ab|\varepsilon|A $

$ S \rightarrow Ld A^\prime M  \xrightarrow{L \rightarrow b L^\prime} S \rightarrow b L^\prime d A^\prime M $

$ A^\prime \rightarrow Lf \xrightarrow{L \rightarrow b L^\prime} A^\prime \rightarrow b L^\prime f $

$P^{\prime \prime}=
\begin{cases}
S \rightarrow b L^\prime d A^\prime M \\\\  
A^\prime \rightarrow b L^\prime f  \\\\   
L^\prime \rightarrow ab | \varepsilon | d A^\prime   \\\\
M \rightarrow aaM|aa  \\\\
\end{cases} $.

$ M \rightarrow aa M^\prime $

$ M^\prime \rightarrow aaM^\prime | \varepsilon $

$ S \rightarrow b L^\prime d A^\prime M \xrightarrow{M \rightarrow aa M^\prime} S \rightarrow b L^\prime d A^\prime aa M^\prime $


$P^{\prime \prime \prime}=
\begin{cases}
S \rightarrow b L^\prime d A^\prime aa M^\prime \\\\  
A^\prime \rightarrow b L^\prime f  \\\\   
L^\prime \rightarrow ab | \varepsilon | d A^\prime   \\\\
M^\prime \rightarrow aaM^\prime | \varepsilon \\\\
\end{cases} $.