![A recursively defined picture](33857.png)
Recursion is used to define sequences, functions, and sets. 
# Sequences
The terms of a sequences are specified using an explicit formula. For instance, the sequence of powers of 2 is given by $a_n=2^n$ for $n=0,1,2,3,\ldots$. The sequence of powers of 2 can also be dfined by giving the first term of the sequence, namely, $a_0=1$, and a rule for finding a term of the sequence from the previous one, namely, $a_{n+1}=2a_n$ for $n=0,1,2,\ldots$. When defining a sequence recursively, we define some initial elements in a basis step and provide a rule for constructing new element. To prove results about recursively defined sets we use a method called *structural induction*.
# Functions
We use two steps to define a function with the set of nonnegative integers as its [domain][Functions#3.1.1 Codomain and Domain]:
## Basis Step
Specify the value of the function at zero.
## Recursive Step
Give a rule for finding its value at an integer from its values at smaller integers.

This definition is called a *recursive* or *inductive definition*. 
## Example
Suppose that $f$ is defined recursively by
$$
\begin{align}
&f(0)=3, \\
&f(n+1)=2f(n)+3.
\end{align}
$$
from the recursive definition it follows that 
$$ 
\begin{align}
&f(1)=2f(0)+3=2 \cdot 3+3=9, \\
&f(2)=2f(1)+3=2*9+3=21, \\
&f(3)=2f(2)+3=2*21+3=45, \\
&f(4)=2f(3)+3=2*45+3=93. \\
\end{align}
$$
# Sets and Structures
As with functions, recursive definitions of sets have two parts, a *basis step* and a *recursive step*. In the basis step, an initial collection of elements is specified. In the recursive step, rules for forming new elements in the set is provided. Recursive definitions may also include an *exclusion rule*. 
## Example
### Basis step
$3 \in S.$
### Recursive Step
If $x \in S$ and $y \in S$, then $x+y \in S$.

By these steps, we can infer that $3+3=6$ is in the set, thereby also $3+6=9$, $6+6=12$ etc. 
# Algorithms
An algorithm is called recursive if it solves a problem by reducing it to an instance of the same problem with smaller input.
## Proving Recursive Algorithms
[[Induction#Mathematical Induction|Mathematical induction]], and its variant [[Induction#Strong Induction|strong induction]], can be used to prove that recursive algorithms are correct i.e. that they produce the desired outputs for all possible input values.
### Examples
#### Example 1
Prove that [[Recursion#Algorithm 2 A Recursive Algorithm for Computing $a n$|Algorithm 2]], which computes powers of real numbers, is correct.
**Basis Step:** If $n=0$, the first step of the algorithm tells us that $power(a,0)=1$. This is correct because $a^0=1$ for every nonzero real number $a$. This completes the basis step.
**Inductive Step:** The inductive hypothesis is the statement that $power(a,k)=a^k$ for all $a \neq 0$ for an arbitrary nonnegative integer $k$. That is, the inductive hypothesis is the statement that the algorithm correctly computes $a^k$. To complete the inductive step, we show that if the inductive hypothesis is true, then the algorithm correctly computes $a^k+1$. Because $k+1$ is a positive integer, when the algorithm computes $a^k+1$, the algorithm sets $power(a,k+1)= a \cdot power(a,k)$. By the inductive hypothesis we have $power(a,k)=a^k$, so $power(a,k+1)=a \cdot power(a,k)=a \cdot a^k=a^{k+1}$. This completes the inductive step.

## Examples
### Algorithm 1: A Recursive Algorithm for Computing $n!$
```ts
const factorial = (n: number) => {
	if (n === 0) return 1;
	else return n * factorial(n-1);
}
```

### Algorithm 2: A Recursive Algorithm for Computing $a^n$
```ts
const power = (a: number, n: number) => {
	if (n === 0) return 1;
	else return a * power(a, n - 1);
}
```
### Algorithm 3: A Recursive Algorithm for Computing $\gcd(a, b)$
```ts
const gcd = (a: number, b: number) => {
	if (a === 0) return b;
	else return gcd(b % a, a);
}
```
# Definitions
## Rooted Trees
The set of rooted trees, where a rooted tree consists of a set of vertices containing a distinguished vertex called the root, and edges connecting these vertices can be defined recursively by these steps
### Basis Step
A single vertex $r$ is a rooted tree.
### Recursive Step
Suppose that $T_1, T_2, \ldots T_n$ are disjoint rooted trees with roots $r_1, r_2, \ldots r_n$ respectively. Then the graph formed by starting with a root $r$, which is not in any of the rooted trees $T_1, T_2, \ldots, T_n$ and adding an edge from $r$ to each of the vertices $r_1, r_2, \ldots, r_n$ is also a rooted tree.
## Binary Trees
Binary trees are a special type of rooted trees. There are two types of binary trees - full binary trees and extended binary trees. In the recursive step of the definition of each type of binary tree, two binary trees are combined to form a new tree with one of these trees designated the left subtree and the other the right subtree. In extended binary trees, the left subtree or the right subtree can be empty, they cannot in full binary trees.
### Extended Binary Trees
The set of extended binary trees can be defined recursively by these steps
#### Basis Step
The empty set is an extended binary tree.
#### Recursive Step
If $T_1$ and $T_2$ are disjoint extended binary trees, there is an extended binary tree, denoted by $T_1 \cdot T_2$, consisting of a root $r$ together with edges connecting the root to each of the roots of the left subtree $T_1$ and the right subtree $T_2$ when these trees are nonempty.

### Full Binary Trees
We define the height $h(T)$ of a full binary tree $T$ recursively.

**Basis Step:** The height of the full binary tree $T$ consisting of only a root $r$ is $h(T)=0$

**Recursive Step:** If $T_1$ and $T_2$ are full binary trees, then the full binary tree $T=T_1 \cdot T_2$ has height $h(T)=1 + \max (h(T_1), h(T_2))$.

The number of vertices of a full binary tree is denoted by $n(T)$ and satisfies the following recursive formula
**Basis Step:** The number of vertices $n(T)$ of a full binary tree $T$ consisting of only a root $r$ is $n(T)=1$.

**Recursive Step:** If $T_1$ and $T_2$ are full binary trees, then the number of vertices of the full binary tree $T=T_1 \cdot T_2$ is $n(T)=1+n(T_1)+n(T_2)$.

If $T$ is a full binary tree, then $n(T) \leq 2^{h(T)+1}-1$.

The set of full binary trees can be defined recursively by these steps
**Basis Step:** There is a full binary tree consisting only of a single vertex $r$.

**Recursive Step:** If $T_1$ and $T_2$ are disjoint full binary trees, there is a full binary tree, denoted by $T_1 \cdot T_2$, consisting of a root $r$ together with edges connecting the root to each of the roots of the left subtree $T_1$ and the right subtree $T_2$. 