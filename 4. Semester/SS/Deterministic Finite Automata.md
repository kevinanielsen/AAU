# Finite Automata
![[dfa definition.png]]

The graphical representation of a DFA is called state diagram.
![[dfa state diagram.png]]

The accept-states are marked with a double-circle. 

Observe, how the DFA above processes string w:
$$
\begin{align}
&w=1101 &\to \text{\textcolor{green}{accept}} \\
&w=001100 &\to \text{\textcolor{green}{accept}} \\
&w=11010 &\to \text{\textcolor{red}{reject}} \\
&w=ε &\to \text{\textcolor{red}{reject}}
\end{align}
$$

# Regular Languages
A language is regular if there exists a DFA that recognizes it.
- The class of regular languages is closed under union, i.e., if $A_1$ and $A_2$ are regular languages, then $A_1\cup A_2$ is also a regular language.
- The class of regular languages is closed under concatenation, i.e., if $A$ and $B$ are regular languages, then $A\circ B$ is also a regular lange.
- The class of regular languages is closed under star operation, i.e., if $A$ is a regular languages, then $A^\star$ is also a regular language.
- The class of regular languages is closed under intersection, i.e., if $A$ and $B$ are regular languages, then $A\cap B$ is also a regular language.
- The class of regular languages is closed under complement, i.e., if $A$ is a regular language, then $\overline A$ is also a regular language.