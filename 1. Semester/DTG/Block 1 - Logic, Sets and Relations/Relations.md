> A binary relation from $A$ to $B$ is a set $R$ of ordered pairs, where the first element of each ordered pair comes from $A$ and the second element comes from $B$

Let $A$ and $B$ be sets. A binary relation from $A$ to $B$ is a subset of $A \bigtimes B$. 
![Visualization of the relation between A and B](14541.png)

The relation is the visualization of the relation $R$ between [[Sets]] $A$ and $B$. Let $A = \{0,1,2\}$ and $B = \{a,b\}$, then $R = \{\{0, a\}, \{0, b\}, \{1, a\}, \{2, b\}\}$.

A set can have a relation to itself. A relation on a set $A$ is a relation from $A$ to $A$ and is a subset of $A \bigtimes A$.
## Examples
$$ 
A = \{1,2,3,4\}
$$
$$
\text{Which ordered pairs are in the relation } R = \{(a, b) \mid \text{a divides b}\}
$$
$$R = \{(1, 1), (1, 2), (1, 3), (1, 4), (2, 2), (2, 4), (3, 3), (4,4)\}$$
![Visualization of the relation above](18348.png)
# Functions
Functions can be used as relations. It is important to note that a function is only a function if a distinct input will always result in the same output. In other words, the function $f(x)=x+2$ will always have $3$ as its output if $1$ is the input.
## Definitions
### Codomain and Domain
If $f$ is a function from $A$ to $B$, we say that $A$ is the *domain* of $f$ and $B$ is the *codomain* of $f$ .
### Image, Preimage, Range and Maps
If $f(a)=b$, we say $b$ is the *image* of $a$ and $a$ is the *preimage* of $b$. The *range*, or *image*, of $f$ is the set of all images of elements of $A$. Also, if $f$ is a function from $A$ to $B$, we say that $f$ *maps* $A$ to $B$.
# Definitions
## Reflexive
A relation is said to be reflexive if $(a,a) \in R$ for every element ${a \in A}$.
### Examples
$$ 
\begin{aligned}
A &= \{1,2,3,4\} \\
R &= \{\{1,1\}, \{2,2\}, \{3,3\}, \{4,4\}\}
\end{aligned}
$$
## Symmetric
A relation is said to be symmetric if $(b,a) \in R$ whenever $(a,b) \in R$, for all $a, b \in A$.
### Examples
$$ 
\begin{aligned}
A &= \{1,2,3,4\} \\
R &= \{\{1,2\}, \{2,1\}\}
\end{aligned}
$$
## Antisymmetric
A relation is called antisymmetric if for all $a,b \in A$, if $(a,b) \in R$ and $(b,a) \in R$, then $a=b$.
### Examples
$$ 
\begin{aligned}
A &= \{1,2,3,4\} \\
R &= \{\{1,2\}, \{3,3\}, \{4,4\}\}
\end{aligned}
$$
## Transitive
A relation $R$ is said to be transitive if whenever $(a,b) \in R$ and $(b,c) \in R$, then $(a,c) \in R$ for all $a,b,c \in R$ 
### Examples
$$ 
\begin{aligned}
A &= \{1,2,3,4\} \\
R &= \{\{1,2\}, \{2,3\}, \{1,3\}\}
\end{aligned}
$$