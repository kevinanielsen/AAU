# 1 Permutations
> A permutation of a set of distinct objects is an ordered arrangement of these objects. We are also interested in ordered arrangements of some of the elements of a set. An ordered arrangement of $r$ elements of a set is called an $r$-permutation.

Let $S=\{1,2,3\}$. The ordered arrangement $3, 1, 2$ is a permutation of $S$. The ordered arrangement $3,2$ is a $2$-permutation of $S$

If $n$ is a positive integer and $r$ is an integer with $1 \leq r \leq n$, then there are
$$
P(n,r)=n(n-1)(n-2)\cdots(n-r+1)
$$
r-permutations of a set with $n$ distinct elements. In other words, if $n$ and $r$ are integers with $0 \leq r \leq n$, then $P(n,r)=\dfrac{n!}{(n-r)!}$.
## 1.1 Examples
1. In how many ways can we select three students from a group of five students to stand in line for a picture? In how many ways can we arrange all five of these students in a line for a picture?
The order of the students matter. There are five ways to pick the first student in the line. Once this student is selected, there are four ways to pick the second. After this, there are three ways to pick the third. By the product rule, there are $5 \cdot 4 \cdot 3 = 60$ ways to pick three students from a group of five to stand in line.

To arrange all five, we continue this down to the last student, that is $5\cdot 4 \cdot 3 \cdot 2 \cdot 1=120$.
2. Let $S=\{a,b,c\}$. The 2-permutations of $S$ are the ordered arrangements $a,b;a,c;b,a;b,c;c,a;c,b$. Consequently, there are six 2-permutations of this set with three elements. There are always six 2-permutations of a set with three elements. There are three ways to choose the first element, then there are two ways to choose the second element, because is must be different from the first element. Hence, by the product rule, we see that $P(3,2)=3 \cdot 2 = 6$.
# 2 Combinations
With combinations, we count the unordered selections of objects.

Let $S$ be the set $\{1,2,3,4\}$. Then $\{1,3,4\}$ is a 3-combination from $S$. Note that $\{4,1,3\}$ is the same 3-combination as we don't care about the order of the list.

The number of r-combinations of a set with $n$ distinct elements is denoted by $C(n,r)$. Note that $C(n,r)$ is also denoted by $\binom{n}{r}$ and is called the *binomial coefficient*. 

The number of r-combinations of a set with $n$ elements, where $n$ is a nonnegative integer and $r$ is an integer with $0 \leq r \leq n$, equals
$$
C(n,r)= \dfrac{n!}{r!(n-r)!}
$$
> [!NOTE] Note
> Let $n$ and $r$ be nonnegative integers with $r \leq n$. Then $C(n,r)=C(n,n-r)$

There are $C(n +r−1, r)= C(n +r−1, n−1)$ _r_-combinations from a set with _n_ elements when repetition of elements is allowed.

## 2.1 Examples
1. How many different committees of three students can be formed from a group of four students?
To answer this question, we need only find the number of subsets with three elements from the set containing the four students. We see that there are four such subsets, one for each of the four students, because choosing three students is the same as choosing one of the four students to leave out the group. This means that there are four ways to choose the committee, when the order does not matter.
2. We see that $C(4,2)=6$, because the 2-combinations of $\{a,b,c,d\}$ are the six subsets $\{a,b\}, \{a,c\}, \{a,d\}, \{b,c\}, \{b,d\}, \{c,d\}$. 
3. How many poker hands of five cards can be dealt from a standard deck of 52 cards? Also, how many ways are there to select 47 cards from a standard deck of 52 cards?
$$
\begin{align}
C(52,5) &= \dfrac{52!}{5!(52-5)!} \\[0.25cm] 
&= \dfrac{52!}{5!47!} = \dfrac{52 \cdot 51 \cdot 50 \cdot 49 \cdot 48}{5 \cdot 4 \cdot 3 \cdot 2 \cdot 1} \\[0.25cm]
&= 26 \cdot 17 \cdot 10 \cdot 49 \cdot 12 = 2.598.960
\end{align}
$$
# 3 Binomial Coefficients and Identities
## 3.1 The Binomial Theorem
A binomial expression is simply the sum of two terms, such as $x+y$. (The terms can be products of constants and variables, but that does not concern us here.)

Let $x$ and $y$ be variables, and let $n$ be a nonnegative integer. Then
$$
(x+y)^n=\sum_{j=0}^n \binom{n}{j} x^{n-j}y^j = \binom{n}{0} x^n + \binom{n}{1} x^{n-1}y+ \cdots + \binom{n}{n-1} xy^{n-1}+ \binom{n}{n} y^n
$$
## 3.2 Corollary
1. Let $n$ be a nonnegative integer. Then
$$
\sum_{k=0}^n \binom{n}{k}=2^n
$$
2. Let $n$ be a positive integer. Then
$$
\sum_{k=0}^n (-1)^k \binom{n}{k}=0.
$$
3. Let $n$ be a nonnegative integer. Then
$$
\sum_{k=0}^n 2^k \binom{n}{k}=3^n.
$$
### 3.2.1 Examples
1. The expansion of $(x+y)^3$ can be found using combinatorial reasoning instead of multiplying the three terms out. When $(x+y)^3=(x+y)(x+y)(x+y)$ is expanded, all products of a term in the first sum, a term in the second sum, and a term in the third sum are added. Terms of the form $x^3,x^2y,xy^2,$ and $y^3$ arise. To obtain a term of the form $x^3$, an $x$ must be chosen in each of the sums, and this can be done in only one way. Thus, the $x^3$ term in the product has a coefficient of 1. To obtain a term of the form $x^2y$, an $x$ must be chosen in two of the three sums (and consequently a $y$ in the other sum). Hence, the number of such terms is the number of 2-combinations of three objects, namely, $\binom32$. Similarly, the number of terms of the form $xy^2$ is the number of ways to pick one of the three sums to obtain an $x$ (and consequently take a $y$ from each of the other two sums). This can be done in $\binom31$ ways. Finally, the only way to obtain a $y^3$ term is to choose the $y$ for each of the three sums in the product, and this can be done in exactly one way.
2. What is the expansion of $(x+y)^4$?
From the binomial theorem it follows that
$$ 
\begin{align}
(x+y)^4 &= \sum_{j=0}^4 \binom4j x^{4-j}y^j \\
&= \binom40 x^4 + \binom41 x^3 y + \binom42 x^2 y^2 + \binom43 xy^3 + \binom44 y^4 \\
&= x^4+4x^3y+6x^2y^2+4xy^3+y^4
\end{align}
$$
3.aligns the coefficient of $x^12y^13$ in the expansion of $(x+y)^{25}$?
From the binomial theorem it follows that this coefficient is 
$$
\binom{25}{13}=\dfrac{25!}{13!12!}=5.200.300
$$
## 3.3 Pascal's Identity and Triangle
### 3.3.1 Pascals Identity
Let $n$ and $k$ be positive integers with $n \geq k$. Then
$$
\binom{n+1}{k}=\binom{n}{k-1}+\binom{n}{k}.
$$
![[80183.png]]
## 3.4 Vandermonde's Identity
Let $m, n,$ and $r$ be nonnegative integers with $r$ not exceeding either $m$ or $n$. Then
$$
\binom{m+n}{r}=\sum_{k=0}^{r} \binom{m}{r-k}\binom{n}{k}.
$$
If $n$ is a nonnegative integer, then
$$
\binom{2n}{n}=\sum_{k=0}^{n} \binom{n}{k}^2.
$$
Let $n$ and $r$ be nonnegative integers with $r \leq n$. Then
$$
\binom{n+1}{r+1}=\sum_{j=r}^{n} \binom{j}{r}.
$$
# 4 Definitions
## 4.1 Combinatorial Proof
A Combinatorial proof of an identity is a proof that uses counting arguments to prove that both sides of the identity count the same objects but in different ways or a proof that is based on showing that there is a bijection between the sets of objects counted by the two sides of the identity. These two types of proofs are called *double counting proofs* and *bijective proofs*, respectively.
