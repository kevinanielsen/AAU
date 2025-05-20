# 1 Literature
Chapter 5 + Slides
# 2 Linear Dependence
A collection or list of $n$-vectors $a_1, \dots, a_k$ (with $k \geq 1$) is called linearly dependent if
$$
\beta_1a_1 + \cdots + \beta_ka_k=0
$$
holds for some $\beta_1, \dots, \beta_k$ that are not all zero. In other words, we can form the zero vector as a [[K01 - Introduction, Vectors, Linearity#4.2 Linear Combinations|linear combination]] of the vectors, with coefficients that are not all zero.

When a collection of vectors is linearly dependent, at least one of the vectors can be expressed as a linear combination of the other vectors.

If any vector in a collection of vectors is a linear combination of the other vectors, then the collection of vectors is linearly dependent.

The vectors
$$ 
\begin{align}
&a_1 = \begin{bmatrix*}[r]
0.2 \\ -7.0 \\ 8.6
\end{bmatrix*}, &a_2 = \begin{bmatrix*}[r]
-0.1 \\ 2.0 \\ -1.0
\end{bmatrix*}, &&a_3 = \begin{bmatrix*}[r]
0.0 \\ -1.0 \\ 2.2
\end{bmatrix*}
\end{align}
$$
are linearly dependent, since $a_1+2a_2-3a_3=0$. We can express any of these vectors as a linear combination of the other two. For example, we have $a_2=(-1/2)a_1+(3/2)a_3$.

![[7300.png]]
## 2.1 Linearly Independent Vectors
A collection of $n$-vectors $a_1, \dots, a_k$ (with $k \geq 1$) is called linearly independent if it is not linearly dependent, which means that 
$$
\beta_1a_1+\cdots+\beta_ka_k=0
$$
if and only if $\beta_1=\cdots=\beta_k=0$. The only linear combination of the vectors that equals the zero vector is the linear combination with all coefficients zero.

Like linear dependence, linear independence is an attribute of a collection of vectors, and not individual vectors.
## 2.2 Linear Combinations of Linearly Independent Vectors
If the $n$-vectors $a_1, \dots, a_k$ are linearly independent and span $\mathbf{R}^n$ (so $k = n$), then every $n$-vector $x$ can be written in exactly one way as a linear combination.
## 2.3 Supersets and Subsets
If a collection of vectors is linearly dependent, then any superset of it is linearly dependent. Any nonempty subset of a linearly independent collection of vectors is linearly independent.
# 3 Basis
## 3.1 Independence-Dimension Inequality
If the $n$-vectors $a_1, \dots, a_k$ are linearly independent, then $k \leq n$. In words: 

> A linearly independent collection of $n$-vectors can have at most $n$ elements.

> Any collection of $n+1$ or more $n$-vectors is linearly dependent.

![[linearly_dependent_vectors.png]]

## 3.2 Basis
A collection of $n$ linearly independent $n$-vectors (i.e., a collection of linearly independent vectors of the maximum possible size) is called a basis. If the $n$-vectors $a_1, \dots, a_n$ are a basis, then any $n$-vector $b$ can be written as a linear combination of them. 
## 3.3 Expansion In a Basis
When we express an $n$-vector $b$ as a linear combination of a basis $a_1, \dots, a_n$, we refer to
$$b=\alpha_1a_1+\cdots+\alpha_na_n,$$
as the expansion of $b$ in the $a_1, \dots , a_n$ basis. The numbers $\alpha_1, \dots, \alpha_n$ are called the coefficients of the expansion of $b$ in the basis $a_1, \dots, a_n$.
# 4 Orthonormal Vectors
A collection of vectors $a_1, \dots, a_k$ is orthogonal or mutually orthogonal if $a_i \perp a_j$ for any $i,j$ with $i\neq j, i,j=1, \dots, k$. A collection of vectors $a_1, \dots, a_k$ is orthonormal if it is orthogonal and $\Vert a_i \Vert = 1$ for $i=1, \dots, k$. (A vector of norm one is called normalized; dividing a vector by its norm is called normalizing it.) In other words, each vector in an orthonormal collection of vectors is normalized, and two different vectors from the collection are orthogonal. Combining the two conditions into one statement:
$$
a_i^Ta_j=\begin{cases}\; 1 &i=j \\ \;0 & i\neq j  \end{cases}
$$
Orthonormality is a attribute of a collection of vectors, and not the individual vector.

## 4.1 Linear Independence of Orthonormal Vectors
Orthonormal vectors are linearly independent.
## 4.2 Orthonormal Basis
If $n$-vectors $a_1, \dots, a_n$ are orthonormal, they are linearly independent, and therefore also a basis. In this case they are called an orthonormal bases.
# 5 Gram-Schmidt Algorithm
The Gram-Schmidt Algorithm can be used to determine if a list of $n$-vectors $a_1, \dots, a_k$ is linearly independent. If the vectors are linearly independent, the algorithm produces an orthonormal collection of vectors $q_1, \dots, q_k$ with the following properties: For each $i=1, \dots, k$, $a_i$ is a linear combination of $q_1, \dots, q_i$, and $q_i$ is a linear combination of $a_1, \dots, a_i$. 

If the vectors $a_1, \dots, a_{j-1}$ are linearly independent, but $a_1, \dots, a_j$ are linearly dependent, the algorithm detects this and terminates. In other words, the algorithm finds the first vector $a_j$ that is a linear combination of previous vectors $a_1, \dots, a_{j-1}$. 
![[gram-schmidt_algorithm.png]]
The orthogonalization step, with $i=1$, reduces to $\tilde q_1 = a_1$. If the algorithm does not quit, i.e., $\tilde q_1, \dots, \tilde q_k$ are all nonzero, we can conclude that the original collection of vectors is linearly independent; if the algorithm does quit early, say, with $\tilde q_j = 0$, we can conclude that the original collection of vectors is linearly dependent (and that $a_j$ is a linear combination of $a_1, \dots, a_{j-1}$).
![[gram-schmidt_illustration.png]]
Orthogonalization step: 
$$
\tilde q_i = a_i - \sum_{j=1}^{i-1}(q_j^Ta_i)q_j
$$
## 5.1 Uses
### 5.1.1 Checking if a collection of vectors is linearly independent. 
Completion of the algorithm means the collection of vectors is linearly independent.
### 5.1.2 Seeing what vector in a collection stops it from being linearly independent.
Early termination at, say $a_j$, means that $a_1, \dots, a_{j-1}$ is linearly independent, but $a_1, \dots, a_j$ is linearly dependent.
### 5.1.3 Checking if a vector is a linear combination of linearly independent vectors.
Early determination at $a_j$ means that $a_j$ can be described as a linear combination of the linearly independent vectors $a_1, \dots, a_{j-1}$. 
### 5.1.4 Checking if a collection of vectors is a basis.
If the algorithm runs till completion on the $n$-vectors $a_1, \dots, a_n$, then they are a basis.