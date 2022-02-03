Student: **Curmanschii Anton, IA1901.**

Construiți gramatica regulată echivalentă automatului finit  dat.

$
AF=(Q, Σ,δ,q_0 ,F), \\\\
Q = \\{ q_0 ,q_1 ,q_2 , q_3 ,q_4 ,q_5 \\}, \\\\
S=\\{a, b, c, d, e, f, i, j \\} \\\\
F=\\{q_5 \\}, \\\\
δ(q_0,a)=\\{q_1 \\},  \\\\
δ(q_1 ,b)=\\{q_2 \\}, 
δ(q_1 ,d)=\\{q_3 \\}, \\\\
δ(q_2 ,c)=\\{q_0 \\},  \\\\
δ(q_3 ,e)=\\{q_4 \\},
δ(q_3 ,i)=\\{q_5 \\},
δ(q_3 ,j)=\\{q_5 \\}, \\\\
δ(q_4 ,f)=\\{q_1 \\} \\\\
$


```mermaid
flowchart LR

q0([q0])
q1([q1])
q2([q2])
q3([q3])
q4([q4])
q5([q5])

q0-- a -->q1

q1-- b -->q2
q1-- d -->q3

q2-- c -->q0

q3-- e -->q4
q3-- i -->q5
q3-- j -->q5

q4-- f -->q1
```

$ a (bca+def) ^ \star d (ef (bca + def) ^ \star d) ^ \star (i + j) $