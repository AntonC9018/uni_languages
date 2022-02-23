$G=(V_N, V_T, P, S), $

$V_n={S,A,B,C,}, $

$V_t={ a,b,c,d}, $

$P=
\begin{cases}
S \rightarrow aABd \\\\  
S \rightarrow aBa  \\\\   
S \rightarrow AC   \\\\
S \rightarrow Ba \\\\
S \rightarrow Cc  \\\\
A \rightarrow bA \\\\
A \rightarrow b  \\\\
A \rightarrow CdC  \\\\ 
A \rightarrow C    \\\\
B \rightarrow SB \\\\
B \rightarrow C   \\\\
C \rightarrow a    \\\\
C \rightarrow Bda
\end{cases}$.

Generați un cuvant utilizând derivarea de dreapta și construiți arborele de derivare.

$ S \xrightarrow{S \rightarrow aABd} aABd \rightarrow \\\\
\xrightarrow{B \rightarrow SB} aASBd \rightarrow \\\\
\xrightarrow{B \rightarrow C} aASCd \rightarrow \\\\
\xrightarrow{C \rightarrow a} aASad \rightarrow \\\\
\xrightarrow{S \rightarrow Cc} aACcad \rightarrow \\\\
\xrightarrow{C \rightarrow Bda} aABdacad \rightarrow \\\\
\xrightarrow{B \rightarrow C} aACdacad \rightarrow \\\\
\xrightarrow{C \rightarrow a} aAadacad \rightarrow \\\\
\xrightarrow{A \rightarrow b} abadacad $


(Ordinea vizualizării poate să nu corespundă ordinii literelor în cuvântul, deoarece se face automat). 

```mermaid
flowchart TD

A0[S] --> A1[a] & A2[A] & A3[B] & A4[d]
A3[B] --> B0[S] & B1[B]
B1[B] --> B2[C]
B2[C] --> B3[a]
B0[S] --> C0[C] & C1[c]
C0[C] --> C2[B] & C3[d] & C4[a]
C2[B] --> C5[C]
C5[C] --> C6[a]
A2[A] --> D0[b]
```