# Laborator 3 la Limbaje formale și automate

A elaborat: **Curmanschii Anton, IA1901.**

Tema: **$\varepsilon$-Producții**

**Varianta 6.**


## Sarcinile

1. Să se elimine $\varepsilon$-producțiile;

2. Să se elimine regulile singulare;

3. Să se elimine simbolurile inutile;

4. Să se genereze două cuvinte și să se construiască arborele de derivare;


## Rezolvările

$ G = (V_T, V_N, P, S) $

$ V_T = \\{ \lnot, \land, \bot, i, j, k, m, \epsilon \\} $

$ V_N = \\{ R, T, I, F, K \\} $

$ S = R $

$ P =
\begin{cases}
R \rightarrow R \lnot T \bot | R \land T \bot | I \\\\
T \rightarrow F | Fi | Fj | Tk | \varepsilon \\\\
F \rightarrow Kk \\\\
K \rightarrow Ki | Km | m \\\\
\end{cases}
$


> 1\. Să se elimine $\varepsilon$-producțiile.

Avem doar o singură $\varepsilon$-producție, anume $ T \rightarrow \varepsilon $.

Peste tot unde avem T în partea dreaptă a altor reguli, anume regulile $ R \rightarrow R \lnot T \bot $,
$ R \rightarrow R \land T \bot $ și $ T \rightarrow Tk $, substituim $ T = \varepsilon $ pentru a produce câte o regulă nouă pentru fiecare caz.

$ (R \rightarrow R \lnot T \bot) \xrightarrow{T = \varepsilon} (R \rightarrow R \lnot \bot); $

$ (R \rightarrow R \land T \bot) \xrightarrow{T = \varepsilon} (R \rightarrow R \land \bot); $

$ (T \rightarrow Tk) \xrightarrow{T = \varepsilon} (T \rightarrow k). $


Primim mulțimea de reguli $ P $ nouă care generează același limbaj, $ P^{\prime} $:

$ P^{\prime} =
\begin{cases}
R \rightarrow R \lnot T \bot | R \lnot \bot | R \land T \bot | R \rightarrow R \land \bot | I \\\\
T \rightarrow F | Fi | Fj | Tk | k \\\\
F \rightarrow Kk \\\\
K \rightarrow Ki | Km | m \\\\
\end{cases}
$


> 2\. Să se elimine regulile singulare.

Regulile singulare sunt regulile de tipul $ A \rightarrow B $. Avem două: $ R \rightarrow I $, $ T \rightarrow F $.
Primul poate fi simplu eliminat, deoarece nu avem nici o altă regulă definită pentru $ I $.

$F$-ul din $ T \rightarrow F $ va fi substituit la definiția lui completă: $ F \rightarrow Kk $.

$ P^{\prime \prime} =
\begin{cases}
R \rightarrow R \lnot T \bot | R \lnot \bot | R \land T \bot | R \rightarrow R \land \bot \\\\
T \rightarrow Kk | Fi | Fj | Tk | k \\\\
F \rightarrow Kk \\\\
K \rightarrow Ki | Km | m \\\\
\end{cases}
$


> 3\. Să se elimine simbolurile inutile.

$
P_1 = \\{ T, K \\} \\\\
P_2 = P_1 \cup \\{ K, F, T \\} = \\{ K, F, T \\} \\\\
P_3 = P_2 \cup \\{ K, F, T \\} = \\{ K, F, T \\} \\\\
P = \\{ K, F, T \\}, \xoverline{P} = V_N \setminus P = \\{ R \\}.
$

Astfel $ R $ este inutil (neproductiv) și poate fi eliminat. 
Intuitiv, substituirea lui $ R $ mereu aduce la recursie infinită.

$ P^{\prime \prime \prime} =
\begin{cases}
T \rightarrow Kk | Fi | Fj | Tk | k \\\\
F \rightarrow Kk \\\\
K \rightarrow Ki | Km | m \\\\
\end{cases}
$

Deoarece $ S = R $, însă $ R $ a fost ștersă în $ P^{\prime \prime \prime} $, nu avem axioma.
Fără axioma toate celelate reguli sunt inaccesibile.

$ P^{\prime \prime \prime \prime} = \emptyset $.


> 4\. Să se genereze două cuvinte și să se construiască arborele de derivare.


Limbajul gramaticii noi $ G^{\prime \prime \prime \prime} = (V_T, V_N, P^{\prime \prime \prime \prime}, S), F(G^{\prime \prime \prime \prime}), $ este vid, deoarece gramatica $ G^{\prime \prime \prime \prime} $ nu conține nici o regulă.
Nu putem construi nici o regulă.