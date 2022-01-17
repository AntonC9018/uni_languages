# Laborator 2 la Limbaje formale și automate

A elaborat: **Curmanschii Anton, IA1901.**

Tema: **Echivalența Gramaticilor Regulate și a Automatelor Finite.**

**Varianta 6.**


## Sarcinile

1. Să se genereze trei forme propoziționale (cuvinte).

2. Să se construiască arborele de derivare pentru fiecare din cuvintele generate.

3. Să se construiască automatul finit echivalent.

4. Printr-un calcul de configurații să se demonstreze că formele propoziționale generate de gramatică sunt acceptate și de automatul finit construit.

5. Să se scrie expresia regulată a cuvintelor generate de gramatica dată.


## Rezolvările

$ G = (V_T, V_N, P, S) $

$ V_T = \\{ 0, 1, c, a \\} $

$ V_N = \\{ E, A, B, C, D \\} $

$ S = E $

$ P =
\begin{cases}
E \rightarrow 0A | c \\\\
A \rightarrow aB | aD \\\\
B \rightarrow bB | 1C | c \\\\
C \rightarrow c \\\\
D \rightarrow aD | 0C | c \\\\
\end{cases}
$


> 1\. Să se genereze trei forme propoziționale (cuvinte).
> 
> 2\. Să se construiască arborele de derivare pentru fiecare din cuvintele generate.

$
E \xrightarrow{ E \rightarrow 0A } 0A 
\xrightarrow{ A \rightarrow aB } 0aB 
\xrightarrow{ B \rightarrow 1C } 0a1C
\xrightarrow{ C \rightarrow c } 0a1c
$

```mermaid
flowchart TD
A0[E] --> A1[0] & A2[A]
A2[A] --> A3[a] & A4[B]
A4[B] --> A5[1] & A6[C]
A6[C] --> A7[c]
```


$
E \xrightarrow{ E \rightarrow 0A } 0A
\xrightarrow{ A \rightarrow aD } 0aD 
\xrightarrow{ D \rightarrow aD } 0aaD 
\xrightarrow{ D \rightarrow 0C } 0aa0C 
\xrightarrow{ C \rightarrow c } 0aa0c
$ 

```mermaid
flowchart TD
A0[E] --> A1[0] & A2[A]
A2[A] --> A3[a] & A4[D]
A4[D] --> A5[a] & A6[D]
A6[D] --> A7[0] & A8[C]
A8[C] --> A9[c]
```


$
E \xrightarrow{ E \rightarrow c } c
$

```mermaid
flowchart TD
A0[E] --> A1[c]
```


$
E \xrightarrow{ E \rightarrow 0A } 0A
\xrightarrow{ A \rightarrow aB } 0aB 
\xrightarrow{ B \rightarrow bB } 0abB 
\xrightarrow{ B \rightarrow bB } 0abbB 
\xrightarrow{ B \rightarrow c } 0abbc
$

```mermaid
flowchart TD
A0[E] --> A1[0] & A2[A]
A2[A] --> A3[a] & A4[B]
A4[B] --> A5[b] & A6[B]
A6[B] --> A7[b] & A8[B]
A8[B] --> A9[c]
```

> 3\. Să se construiască automatul finit echivalent.

Automatul finit: $ 
AF = (Q, \Sigma, \delta, q_E, F), \\\\
Q = \\{ q_E, q_A, q_B, q_D, q_C, q_Z \\},   \\\\
\Sigma = \\{ a, b, 0, 1 \\},         \\\\
F = \\{ q_Z \\},                  \\\\
\delta(q_E, c) =\\{ q_Z \\}, \delta(q_E, 0) = \\{ q_A \\}, \\\\ 
\delta(q_A, a) = \\{ q_B, q_D \\}, \\\\
\delta(q_{B}, b) = \\{ q_B \\}, \delta(q_{B}, 1) = \\{ q_C \\}, \delta(q_{B}, c) = \\{ q_Z \\}, \\\\
\delta(q_{D}, a) = \\{ q_D \\}, \delta(q_{D}, 0) = \\{ q_C \\}, \delta(q_{D}, c) = \\{ q_Z \\}, \\\\
\delta(q_{C}, c) = \\{ q_Z \\}.
$

```mermaid
flowchart LR

E(["q_E"])
A(["q_A"])
B(["q_B"])
D(["q_D"])
C(["q_C"])
Z(["q_Z"])

E-- c -->Z
E-- 0 -->A

A-- a -->B & D

B-- "b" -->B
D-- "a" -->D

B-- "1" -->C
D-- "0" -->C

B & D-- c -->Z

C-- c -->Z
```


> 4\. Printr-un calcul de configurații să se demonstreze că formele propoziționale generate de gramatică sunt acceptate și de automatul finit construit.

Și în a doua variantă a automatului:

1. **0a1c**

$ (q_E, 0a1c) \vdash (q_A, a1c) \vdash (q_D, 1c) \vdash (q_C, c) \vdash (q_Z, \varepsilon) $

2. **0aa0c**

$ (q_E, 0aa0c) \vdash (q_A, aa0c) \vdash (q_D, a0c) \vdash (q_D, 0c) \vdash (q_C, c) \vdash (q_Z, \varepsilon) $

3. **c**

$ (q_E, c) \vdash (q_Z, \varepsilon) $

4. **0abbc**

$ (q_E, 0abbc) \vdash (q_A, abbc) \vdash (q_B, bbc) \vdash (q_B, bc) \vdash (q_B, c) \vdash (q_Z, \varepsilon) $


> 5\. Să se scrie expresia regulată a cuvintelor generate de gramatica dată.


Un *c* sau (*0* urmat de (*a*, ((orice număr de *b*, (*1c* sau *c*)) sau (orice număr de *a*, (*0c* sau *c*))))).

$ c + (0a(b^{\star} (1c + c) + a^{\star} (0c + c))) $

Parantezele pot fi omise.

$ c + 0a(b^{\star} (1c + c) + a^{\star} (0c + c)) $

Pentru claritate poate fi folosit și simbolul operatorului de concatenare, ".".

$ c + 0.a.(b^{\star}.(1.c + c) + a^{\star}.(0.c + c)) $

Dacă se dorește să se folosească și $\varepsilon$:

$ (\varepsilon + 0a(b^{\star}(1 + \varepsilon) + a^{\star}(0 + \varepsilon))c $
