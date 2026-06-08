Q16
$$\dfrac{\Gamma \vdash e_1 : \tau_1 \quad \Gamma \vdash e_2 : \tau_2}{\Gamma \vdash (e_1, e_2):(\tau_1 \times \tau_2)}$$
$$
\dfrac{\Gamma \vdash e : (\tau_1 \times \tau_2)}{\Gamma \vdash e.1 : \tau_1} \quad \dfrac{\Gamma \vdash e : (\tau_1 \times \tau_2)}{\Gamma \vdash e.2 : \tau_2}
$$
Q17
Because the program can either result in a pair type $(x.2, x.1+x.2)$ or an integer type $0$, the program would not run in a *static* type system, where the return value would need to have the same type in all cases.

Q18
$$

$$
Q19
$$
\dfrac{\Gamma \vdash e_1 : \texttt{int} \quad \Gamma \vdash e_2 : \texttt{int} \quad \Gamma \vdash s}{\Gamma \vdash \texttt{for $i = e_1$ to $e_2$ do $s$}}
$$
Q20
No, $\texttt p$ is being rewritten from $\texttt{int}$ to a pair type as part of the loop. Except from that part, our static typing system L would allow this type of encoding because the pair type $(\tau \times \tau)$ doesn't have any restrictions for each of the two components, locking them to a certain type.

Q21
B

Q22
A

Q23
C

Q24
D
