Student: **Curmanschii Anton, IA1901.**


Construiți automatul finit pentru expresia regulată $ e= (a+b) * ad (a+bc) c * $


$ 
AF = (Q, \Sigma, \delta, q _ 0, F) \\\\
Q = \\{ q _ 0, q _ 1, q _ 2, q _ 3, q _ 4 \\} \\\\
\Sigma = \\{ a, b, c, d \\} \\\\
F = \\{ q _ 4 \\} \\\\
\delta(q _ 0, a) = \\{ q _ 0, q _ 1 \\}, \delta(q _ 0, b) = \\{ q _ 0 \\} \\\\
\delta(q _ 1, d) = \\{ q _ 2 \\}, \\\\
\delta(q _ 2, a) = \\{ q _ 4 \\}, \delta(q _ 2, b) = \\{ q _ 3 \\} \\\\
\delta(q _ 3, c) = \\{ q _ 4 \\} \\\\
\delta(q _ 4, c) = \\{ q _ 4 \\}
$


```mermaid
flowchart LR

q0([q0])
q1([q1])
q2([q2])
q3([q3])
q4([q4])

q0-- a -->q0
q0-- b -->q0

q0-- a -->q1

q1-- d -->q2

q2-- b -->q3
q2-- a -->q4

q3-- c -->q4

q4-- c -->q4
```