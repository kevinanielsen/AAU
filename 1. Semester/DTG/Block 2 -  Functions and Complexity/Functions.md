Let $A$ and $B$ be nonempty sets. A function $f$ from $A$ to $B$ is an assignment of exactly one element of $B$ to each element of $A$. We write $f(a) = b$ if $b$ is the unique element of $B$ assigned by the function $f$ to the element $a$ of $A$. If $f$ is a function from $A$ to $B$, we write $f: a \rightarrow B$.

Other names for functions are *mappings* or *transformations*.

The codomain is the set of possible values of the function and the range is the set of all elements of the codomain that are achieved as the value of $f$ for at least one element of the domain.

We say that two functions are equal when they have the same domain, have the same codomain and map each element of their common domain to the same element in their common codomain.

Let $f_1$ and $f_2$ be functions from $A$ to $\mathbf{R}$. Then $f_1 + f_2$ and $f_1 f_2$ are also functions from $A$ to $\mathbf{R}$ defined for all $x \in A$ by
$$
\begin{aligned}
(f_1 + f_2)(x) &= f_1(x) + f_2(x), \\ 
(f_1 f_2)(x) &= f_1(x)f_2(x)
\end{aligned}
$$
## 0.1 Example
$$ 
\begin{aligned}
f_1 &= x^2 \\
f_2 &= x - x^2 \\\\
f_1 + f_2 &= \\ 
(f_1+f_2)(x) &= \\ 
f_1(x)+f_2(x) &= x^2 + (x - x^2) = x \\\\
(f_1 f_2)(x) &= x^2(x-x^2) = x^3 - x^4
\end{aligned}
$$

Let $f$ be a function from $A$ to $B$ and let $S$ be a subset of $A$. The image of $S$ under the function $f$ is the subset of $B$ that consists of the images of elements of $S$. We denote the image of $S$ by $f(S)$, so 
$$f(S) = \{t \mid \exists s \in S (t = f(s))\}$$
This can be written with a shorthand $\{f(s) \mid s \in S\}$.
# 1 Inverse functions
The inverse of a function $f$ is denoted by $f^{-1}$. A function cannot be inverted unless it is bijective. This is because an element in the domain cannot have multiple images. I.e. a singular input must also have a single output. Furthermore, all elements in the domains must have images i.e. all inputs must have an output.
# 2 Compositions
Let $g$ be a function from the set $A$ to the set $B$ and let $f$ be a function from the set $B$ to the set $C$. The composition of the functions $f$ and $g$, denoted for all $a \in A$ by $f \circ g$ is the function from $A$ to $C$ defined by
$$(f \circ g)(a) = f(g(a))$$
![[91575.png]]
## 2.1 Examples
$$ 
\begin{aligned}
f(x) &= 2x + 3 \\
g(x) &= 3x + 2 \\\\
(f \circ g)(x) &= \\
f(g(x)) &= \\
f(3x+2) &= 2(3x + 2) + 3 = 6x+7 \\\\
(g \circ f)(x) &= \\
g(f(x)) &= \\
g(2x+3) &= 3(2x + 3) + 2 = 6x + 11
\end{aligned}
$$
# 3 Definitions
### 3.1.1 Codomain and Domain
If $f$ is a function from $A$ to $B$, we say that $A$ is the *domain* of $f$ and $B$ is the *codomain* of $f$ .
### 3.1.2 Image, Preimage, Range and Maps
If $f(a)=b$, we say $b$ is the *image* of $a$ and $a$ is the *preimage* of $b$. The *range*, or *image*, of $f$ is the set of all images of elements of $A$. Also, if $f$ is a function from $A$ to $B$, we say that $f$ *maps* $A$ to $B$.
### 3.1.3 Examples
$$ 
\begin{aligned}
A &= \{a,b,c,d,e\} \\
B &= \{1,2,3,4\} \\
f(a) &= 2 \\
f(b) &= 1 \\
f(c) &= 4 \\
f(d) &= 1 \\
f(e) &= 1 \\
\end{aligned}
$$
The image of the subset $S=\{b,c,d\}$ is the set $f(S)=\{1,4\}$
## 3.2 One-to-One Functions / Injection
One-to-One functions never assign the same value to two different domain elements. A function $f$ that is said to be *one-to-one*, or an *injection*, if and only if $f(a)=f(b)$ implies that $a=b$ for all $a$ and $b$ in the domain of $f$. 
One-to-Ones / Injections can be expressed by $\forall a \forall b (f(a)=f(b) \rightarrow a = b)$ or equivalently $\forall a \forall b (a \neq b \rightarrow f(a) \neq f(b))$

![A one-to-one function](40091.png)
## 3.3 Onto / Surjection
A function $f$ from $A$ to $B$ is called onto, or a surjection, if and only if for every element $b \in B$ there is an element $a \in A$ with $f(a)=b$. In other words, every element in the codomain $B$ must be the image of some element in the domain $A$.

> Consider the function _f_ in Example 11 that assigns jobs to workers. The function _f_ is onto if for every job there is a worker assigned this job. The function _f_ is not onto when there is at least one job that has no worker assigned it.

![An onto function](69596.png)

## 3.4 One-to-One correspondence / Bijection
A function is said to be bijective if it is both one-to-one and onto. E.g. both surjective and injective.
## 3.5 Increasing / Decreasing functions
A function is said to be increasing if $f(x) \le f(y)$, and strictly increasing if $f(x) < f(y)$ whenever $x < y$ and $x$ and $y$ are in the domain of $f$.

A function is said to be decreasing if the reverse is true e.g. decreasing if $f(x) \ge f(y)$ and strictly decreasing if $f(x) > f(y)$ whenever $x < y$ and $x$ and $y$ are in the domain of $f$.

![[71842.png]]
## 3.6 Graph
Let $f$ be a function from the set $A$ to the set $B$. The graph of the function $f$ is the set of ordered pairs $\{(a,b) \mid a \in A \text{ and } f(a) = b\}$. 

## 3.7 Floor
The floor function, denoted by $\lfloor x \rfloor$, assigns to the real number $x$ the largest integer that is less than or equal to $x$. 
### 3.7.1 Examples
$$ 
\begin{aligned}
\lfloor 3.8 \rfloor &= 3 \\
\lfloor 9.3 \rfloor &= 9 \\
\lfloor 4 \rfloor &= 4
\end{aligned}
$$
## 3.8 Ceiling
The ceiling function, denoted by $\lceil x \rceil$, assigns to the real number $x$ the smallest integer that is greater than or equal to $x$.
### 3.8.1 Examples
$$ 
\begin{aligned}
\lceil 3.8 \rceil &= 4 \\
\lceil 9.3 \rceil &= 10 \\
\lceil 4 \rceil &= 4
\end{aligned}
$$
## 3.9 Partial Functions
Partial functions are functions where some inputs results in undefined outputs. E.g. the "youngest child" function, which would be undefined for couples having no children.