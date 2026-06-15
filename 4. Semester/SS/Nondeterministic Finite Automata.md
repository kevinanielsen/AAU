![[nodeterministic computation.png|Nondeterministic Computation|600]]

![[nfa definition.png|Nondeterministic Finite Automata definition|600]]

![[parallelism.png|Parallelism|600]]

![[nondeterministic computations definition.png|Nondeterministic Computations|600]]

![[dfas are nfas.png|DFAs are NFAs|600]]

Every NFA has an equivalent DFA, i.e., for every NFA $N$ there exists a DFA $M$ such that $\mathcal{L}(N)=\mathcal L (M)$.

![[nfa to dfa example.png|NFA to DFA Example|600]]

# Closure Under Regular Operations
- The class of regular languages is closed under union, i.e., if $A$ and $B$ are regular languages, then $A \cup B$ is also a regular language.
- The class of regular languages is closed under concatenation, i.e., if $A$ and $B$ are regular languages, then $A \circ B$ is also a regular language.
- The class of regular languages is closed under star operation, i.e., if $A$ is a regular languages, then $A^\star$ is also a regular language.