Fie gramatica independentă de context 

$ G=(V_N, V_T, P, S), \\\\
V_N=\\{S,A,B,M\\}, \\\\ 
V_T=\\{ a, b, d\\}, \\\\
P=
\begin{cases}
S \rightarrow aMa|Md|CA|M|A \\\\  
A \rightarrow bA|b|CdC|C  \\\\   
B \rightarrow SM  \\\\
M \rightarrow b  \\\\
C \rightarrow a|Mda  \\\\
\end{cases} $.

Construiţi gramatica independentă de context echivalentă  eliminând  regulile singulare (redenumiri).


$ S \rightarrow M \xrightarrow{M \rightarrow b} S \rightarrow b $

$ A \rightarrow C \xrightarrow{C \rightarrow a|Mda} A \rightarrow a|Mda $

$ S \rightarrow A \xrightarrow{A \rightarrow bA|b|CdC|a|Mda} S \rightarrow bA|b|CdC|a|Mda $


$ P^\prime=
\begin{cases}
S \rightarrow aMa|Md|CA|b|bA|b|CdC|a|Mda \\\\  
A \rightarrow bA|b|CdC|a|Mda  \\\\   
B \rightarrow SM  \\\\
M \rightarrow b  \\\\
C \rightarrow a|Mda  \\\\
\end{cases} $.