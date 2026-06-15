![[context-free grammar definition.png|Context-Free Grammar Definition|600]]
![[context free language definition.png|Context-Free Language Definition]]
# Conversion From DFA to CFG
![[conversion from dfa to cfg example.png|Conversion From DFA to CFG Example|600]]
# Closures
- Context-free languages are closed under union, concatenation, and star operation.
- Context-free languages are **not** closed under complement, i.e., there exists a CFG $G$ with terminals $\Sigma$ such that  $\Sigma^\star \backslash \mathcal L (G)$ is not a CFL.
- Context-free languages are **not** closed under intersection, i.e., there exists CFGs $G$ and $G'$ such that $\mathcal L (G) \cap \mathcal L (G')$ is not a CFL.
