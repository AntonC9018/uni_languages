
$ G = (V_T, V_N, P, S) $

$ V_T = \\{ a, b, c \\} $

$ V_N = \\{ S, D \\} $

$ P =
\begin{cases}
S \rightarrow Dc \\\\
D \rightarrow DD | \varepsilon | aDb \\\\
\end{cases}
$

Eliminați $\varepsilon$-producțiile.

$ D \rightarrow \varepsilon $

Substituim în orice reguli care implică D pentru a crea câte o regulă nouă pentru fiecare altă regulă.

$ S \rightarrow Dc \xrightarrow{ D \rightarrow \varepsilon } S \rightarrow c $

$ D \rightarrow DD \xrightarrow{ D \rightarrow \varepsilon } D \rightarrow \varepsilon $

$ D \rightarrow aDb \xrightarrow{ D \rightarrow \varepsilon } D \rightarrow ab $

După ce eliminăm regula $D \rightarrow \varepsilon$.

Am obținut următoarele reguli:

$ P^{\prime} =
\begin{cases}
S \rightarrow Dc | c \\\\
D \rightarrow DD | ab | aDb \\\\
\end{cases}
$
