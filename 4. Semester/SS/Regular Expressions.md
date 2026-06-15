![[regular expressions definition.png|Regular Expression Definition]]
# Rules
- The concatenation $R_1 \circ R_2$ is abbreviated as $R_1 R_2$.
- $\{a_1, a_2, \dots, a_n\}$ denotes the expression $a_1 \cup a_2 \cup \dots \cup a_n$.
- $R^+ = RR^\star$
- $R^k$ denotes concatenation of $k$ copies of $R$.
## Precedence
To avoid clutter, we apply a precedence of operations:
- Star operation is applied first,
- followed by concatenation,
- followed by union,
- e.g., $0 \circ 1^\star \cup 0 = (0 \circ (1^\star ))\cup 0$
# Examples
1. $0^\star 10^\star = \{w \;|\; w \text{ contains a single 1}\}$
2. $\Sigma^\star1\Sigma^\star = \{w\;|\; w\text{ contains at least 1}\}$
3. $\Sigma^\star 001 \Sigma^\star = \{w\;|\; w\text{ contains the substring 001}\}$
4. $(01 \cup 1)^\star=\{w\;|\; \text{every 0 in \textit{w} is followed by at least one 1}\}$
5. $(\Sigma\Sigma)^\star = \{w\;|\; w\text{ is a string of even length}\}$
6. $01 \cup 10 = \{01, 10\}$
7. $0\Sigma^\star 0 \cup 1 \Sigma^\star 1 \cup \Sigma=\{w\;|\; w\text{ starts and ends with the same symbol}\}$

![[regular expression equivalence with finite automata.png|Equivalence with Finite Automata|600]]
# Generalized Nondeterministic Finite Automata
![[Generalized Nondeterministic Finite Automata.png|Generalized Nondeterministic Finite Automata|600]]
![[gnfa example.png|GNFA Example|600]]
![[gnfa definition.png|GNFA Definition|600]]

