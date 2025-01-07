> A set is an unordered collection of distinct objects, called *elements* or *members* of the sets. A set is said to *contain* its elements. We write  $a \in A$ to denote that $a$ is an element of the set $A$. The notation $a \notin A$ denotes that $a$ is not an element of the set $A$ 

# 1 Set Builder Notation
Set builder notation is another way of describing sets. The set $O$ of all odd positive integers less that 10 can be written as 

$O=\{x \mid x$ is an odd positive integer less than 10$\}$

This notation is typically used to describe sets when it is impossible to list all the elements of the set. For instance the set $\mathbf{Q}^{+}$ of all positive rational numbers can be written as
$$\mathbf{Q}^{+} = \left\{ x \in \mathbf{R} \mid x = \frac{p}{q}, \text{ for some positive integers } p \text{ and } q \right\}.$$
Two sets are **equal** if and only if they have the same elements. Therefore, if $A$ and $B$ are sets, then $A$ and $B$ are equal if $\forall{x}(x \in A \leftrightarrow x \in B)$. We write $A=B$ if $A$ and $B$ are equal sets.
# 2 Venn Diagrams
Venn Diagrams can be used to represent sets graphically. 
![**Venn diagram for the set of vowels.**](22800.png)

# 3 Subsets
We see that $A \subseteq B$ if and only if the quantification $$\forall{x}(x \in A \to x \in B)$$
is true. To show that $A$ is not a subset of $B$ we therefore only need to find one element $x \in A$ with $x \notin B$. 

> [!NOTE] Theorems
> * For every set $S$, it holds that $$
> \emptyset \subseteq S \text{ and } S \subseteq S
> $$. 
> * If the sets $A$ and $B$ are finite sets, it holds that 
> $$
> \left| A \cup B \right| = \left| A \right| + \left| B \right| - \left| A \cap B \right|
> $$
## 3.1 Set Identities

| **Identity**                                                                                                     | **Name**                    |
| ---------------------------------------------------------------------------------------------------------------- | --------------------------- |
| $A \cap U = A$<br>$A \cup \emptyset = A$                                                                         | Identity laws               |
| $A \cup A = A$<br>$A \cap A = A$                                                                                 | Idempotent laws             |
| $\bar{A} = A$<br>$\bar{\bar{A}} = A$                                                                             | Complementation law         |
| $A \cup B = B \cup A$<br>$A \cap B = B \cap A$                                                                   | Commutative laws            |
| $A \cup (B \cup C) = (A \cup B) \cup C$<br>$A \cap (B \cap C) = (A \cap B) \cap C$                               | Associative laws            |
| $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$<br>$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$             | Distributive laws           |
| $\overline{A \cap B} = \overline{A} \cup \overline{B}$<br>$\overline{A \cup B} = \overline{A} \cap \overline{B}$ | De Morgan’s laws (for sets) |
| $A \cup (A \cap B) = A$<br>$A \cap (A \cup B) = A$                                                               | Absorption laws             |
| $A \cup \overline{A} = U$<br>$A \cap \overline{A} = \emptyset$                                                   | Complement laws             |

## 3.2 Set operations
## 3.3 Membership tables
Membership tables are closely related to [[Logic#Truth Tables]]. When filling out membership tables, you could think of the union operator $\cup$ as the *or* operator $\vee$ from propositional logic, and the intersection $\cap$ can be thought of as the *and* operator $\wedge$.

|  A  |  B  |  C  | $B \cap C$ | $A \cup (B \cap C)$ | $A \cup C$ | $(A \cup B) \cap (A \cup C)$ |
| :-: | :-: | :-: | :--------: | :-----------------: | :--------: | :--------------------------: |
|  1  |  1  |  1  |     1      |          1          |     1      |              1               |
|  1  |  1  |  0  |     0      |          1          |     1      |              0               |
|  1  |  0  |  1  |     0      |          1          |     1      |              1               |
|  0  |  1  |  0  |     0      |          0          |     0      |              0               |
|  0  |  0  |  1  |     0      |          0          |     1      |              0               |
|  0  |  0  |  0  |     0      |          0          |     0      |              0               |

# 4 Definitions
## 4.1 Important Sets
$\mathbf{N} = \{0,1,2,3, ...\} \text{, the set of all } \textbf{natural numbers.}$
$\mathbf{Z} = \{..., -2, -1, 0,1,2, ...\} \text{, the set of all } \textbf{integers.}$
$\mathbf{Z}^{+} = \{1,2, ...\}\text{, the set of all }\mathbf{positive\ integers.}$
$\mathbf{Q} = \left\{ \frac{p}{q} \mid p \in \mathbf{Z}, q \in \mathbf{Z}, q \neq 0 \right\} \text{, the set of all } \mathbf{rational\ numbers.}$
$\mathbf{R} \text{, the set of all } \mathbf{real\ numbers.}$
## 4.2 Subset
The set $A$ is a subset of $B$, if and only if every element of $A$ is also an element of $B$. The notation $A \subseteq B$ describes that set $A$ is a subset of set $B$.
## 4.3 Superset
The set $B$ is a superset of set $A$, if every element of $A$ is also an element of $B$. The notation $B \supseteq A$ describes that set $B$ is a superset of set $A$. 

$A \subseteq B$ and $B \supseteq A$ are equivalent statements.
## 4.4 Empty Set
To denote an empty set, we use $\emptyset$. An empty set, $\emptyset$, is a set with no elements, therefore it follows that $x \in \emptyset$ is always false.
## 4.5 Proper Subset
A proper subset is when set $A$ is a subset of set $B$ but that $A \neq B$. We write $A \subset B$ to denote that $A$ is a proper subset of $B$. A set $A$ would be considered a proper subset of $B$ if and only if
$$\forall x (x \in A \to x \in B) \wedge \exists x (x \in B \wedge x \notin A)$$
In other words: If we call the first part of the proposition $p$ and the second, $q$ 
- **p**: All elements in set $A$ are also in set $B$, and for any $x$ not in $A$, the implication $x \in A \to x \in B$ holds by default.
- **q**: There exists at least one element in $B$ that is not in $A$.
## 4.6 Cardinality
The cardinality of a set, or the cardinal number of a set, is the number of distinct elements in a finite set. The cardinality of a set $S$ is denoted by $\left| S \right|$ 
### 4.6.1 Examples
$$ 
\begin{align}
S &= \{1,2,3\} \\
\left| S \right| &= 3
\end{align}
$$
## 4.7 Union
The union of sets $A$ and $B$ is denoted by $A \cup B$ and it is the set that contains those elements that are either in $A$ or in $B$, or in both. This tells us that
$$
A \cup B = \{x \mid x \in A \vee x \in B\}
$$
The union of a collection of sets is the set that contain those elements that are members of at least one set in the collection and can be described with the following notation
$$A_1 \cup A_2 \cup \cdots \cup A_n=\bigcup_{i=1}^n A_i$$
### 4.7.1 Examples
$$
\begin{align}
A &= \{1,2,3\} \\
B &= \{3,4,5\} \\
A \cup B &= \{1,2,3,4,5\}
\end{align}
$$
## 4.8 Intersection
The intersection of the sets $A$ and $B$ is denoted by $A \cap B$ and is the set of elements that exist both in set $A$ and $B$. This tells us that 
$$
A \cap B = \{x \mid x \in A \wedge x \in B\}
$$
The intersection of a collection of sets can be described with the following notation
$$A_1 \cap A_2 \cap \cdots \cap A_n=\bigcap_{i=1}^n A_i$$
### 4.8.1 Examples
$$
\begin{align}
A = \{1, 2, 3\} \\
B = \{3, 4, 5\} \\
A \cap B = \{3\}
\end{align}
$$
## 4.9 Disjoint
Two sets are called disjoint if their intersection is the empty set.
### 4.9.1 Examples
$$ 
\begin{align}
A &= \{1,2,3\} \\
B &= \{4,5\} \\
A \cap B &= \{\}
\end{align}
$$
## 4.10 Difference
The difference between two sets $A$ and $B$ is denoted by $A - B$ and is the set containing those elements that are in $A$ but not in $B$. The difference of $A$ and $B$ is also called the *complement of $B$ with respect to $A$.* The difference between the sets $A$ and $B$ can also be denoted with $A \setminus B$.

![Difference between sets A and B](90271.png)
### 4.10.1 Examples
$$ 
\begin{align}
A &= \{1,2,3\} \\
B &= \{3,4,5\}\\
A \setminus B &= \{1,2\}
\end{align}
$$
## 4.11 Complement
The complement of a set is a set of all the elements that are not in said set. To denote the complement of a set $A$, you would write it like the following.
$$
\bar{A} = \{ x \in U \mid x \notin A \}
$$
It could also be denoted with $U \setminus A$.
Taking the complement of a complement set would negate the complement, therefore it holds that $\bar{\bar{A}} = A$
![Complement of a set](39258.png)
## 4.12 Power Sets
A power set is the set of all possible subsets of a set. Given the set $S$, the power set would be denoted by $\mathcal{P}(S)$.

The cardinality of a power set of $A$ can be found taking 2 to the power of the cardinality of the set $A$.
### 4.12.1 Examples
$$
\begin{align}
S &= \{1, 2, 3\} \\
\mathcal{P}(S) &= \{\emptyset, \{1\}, \{2\}, \{3\}, \{1,2\}, \{1,3\}, \{2,3\}, \{1,2,3\}\} \\ \\
\left| S \right| &= 3 \\
\left| \mathcal{P}(S) \right| &= 2^\left|S\right| = 2^3 = 8
\end{align}
$$
## 4.13 Ordered Pair
An ordered pair $(a,b)$ is a set $\{\{a\}, \{a, b\}\}$
### 4.13.1 Examples
$$ 
\begin{align}
(1,2) &= \{\{1\}, \{1, 2\}\} \\
(2,1) &= \{\{2\}, \{2, 1\}\}
\end{align}
$$
## 4.14 Cartesian Products
The cartesian product (or *cross product*) of two sets is the set of all ordered pairs $(a,b)$, where $a \in A$ and $b \in B$. Hence, 
$$
A \bigtimes B = \{(a,b) \mid a \in A \wedge b \in B\}
$$
The cartesian product of two sets $A$, $B$, is denoted by $A \bigtimes B$ . 

Finding the cardinality of the cartesian product of two sets is simply multiplying the cardinality of each of the sets. If $\left|A\right| = m$ and $\left|b\right| = n$ then $\left| A \bigtimes B \right| = m*n$

The cartesian product can be found even with more than two sets. 
* **3-tuple:** $A \bigtimes B \bigtimes C = \{(a,b,c) \mid a \in A, b \in B, c \in C\}$
* **n-tuple:** $A_1 \times A_2 \times \cdots \times A_n = \left\{ (a_1, a_2, \dots, a_n) \mid a_1 \in A_1, a_2 \in A_2, \dots, a_n \in A_n \right\}$
### 4.14.1 Examples
$$ 
\begin{align}
A &= \{1,2\} \\
B &= \{a,b,c\} \\
A \bigtimes B &= \{\{1, a\}, \{1, b\}, \{1, c\}, \{2,a\}, \{2, b\}, \{2, c\}\} \\
B \bigtimes A &= \{\{a, 1\}, \{a, 2\}, \{b, 1\}, \{b,2\}, \{c, 1\}, \{c, 2\}\} \\ \\
\left| A \right| &= 2 \\
\left| B \right| &= 3 \\
\left| A \bigtimes B \right| &= 6
\end{align}
$$

