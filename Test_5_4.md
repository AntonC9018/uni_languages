Fie gramatica independentă de context 

$ G=(V_N, V_T, P, E), \\\\
V_N=\\{E,T,F\\}, \\\\ 
V_T=\\{ a, b, c, d, +, -, * , /, (, )\\}, \\\\
P=
\begin{cases}
E \rightarrow T|E+T|E-T \\\\  
T \rightarrow F|T * F| T / F  \\\\   
F \rightarrow (E)|a|b|c|d  \\\\
\end{cases} $.

Determinați  derivarea de stânga a   cuvântului  `d+(c+a*c)/a`   și construiți arborele de derivare.


$ E \xrightarrow{E \rightarrow E+T} E \rightarrow E+T \\\\
\xrightarrow{E \rightarrow T} T+T \rightarrow \\\\
\xrightarrow{T \rightarrow F} F+T \rightarrow \\\\
\xrightarrow{F \rightarrow d} d+T \rightarrow \\\\
\xrightarrow{T \rightarrow T/F} d+T/F \rightarrow \\\\
\xrightarrow{T \rightarrow (E)} d+(E)/F \rightarrow \\\\
\xrightarrow{E \rightarrow E+T} d+(E+T)/F \rightarrow \\\\
\xrightarrow{E \rightarrow T} d+(T+T)/F \rightarrow \\\\
\xrightarrow{T \rightarrow F} d+(F+T)/F \rightarrow \\\\
\xrightarrow{F \rightarrow c} d+(c+T)/F \rightarrow \\\\
\xrightarrow{T \rightarrow T * F} d+(c+T * F)/F \rightarrow \\\\
\xrightarrow{T \rightarrow F} d+(c+F * F)/F \rightarrow \\\\
\xrightarrow{F \rightarrow a} d+(c+a * F)/F \rightarrow \\\\
\xrightarrow{F \rightarrow c} d+(c+a * c)/F \rightarrow \\\\
\xrightarrow{F \rightarrow a} d+(c+a * c)/a $


(Ordinea vizualizării poate să nu corespundă ordinii literelor în cuvântul, deoarece se face automat). 

```mermaid
flowchart TD

A0[E] --> A1[E] & A2["+"] & A3[T]
A1[E] --> B1[T]
B1[T] --> C1[F]
C1[F] --> D0[d]

A3[T] --> B3[T] & B4["/"] & B5[F]

B3[T] --> E0["("] & E1[E] & E2[")"]

E1[E] --> G0[E] & G1["+"] & G2[T]

G0[E] --> F0[T]
F0[T] --> H0[F]
H0[F] --> I0[c]

G2[T] --> G3[T] & G4["*"] & G5[F]
G3[T] --> H5[F]
H5[F] --> G6[a]
G5[F] --> H6[c]

B5[F] --> U1[a]
```