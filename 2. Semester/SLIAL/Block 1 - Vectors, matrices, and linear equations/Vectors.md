A *vector* is an ordered finite list of numbers. Vectors are usually written as vertical arrays, surrounded by square or curved brackets, as in
$$
\begin{bmatrix}
-1.1 \\
0.0 \\
3.6 \\
-7.2
\end{bmatrix}
\quad
\text{or}
\quad
\begin{pmatrix}
-1.1 \\
0.0 \\
3.6 \\
-7.2
\end{pmatrix}
$$
But can also be written as numbers separated by commas and surrounded by parentheses like
$$
(-1.1,0.0,3.6,-7.2).
$$
The numbers of the vector are called *elements* (or *entries*, *coefficients*, *components*). The *size* (or *dimension*, *length*) of the vector is the number of elements it contains.

A *n-vector* has $n$ elements. A 1-vector is considered to be the same as a number, i.e. the 1-vector $[1.3]$ and the number 1.3 are considered the same.

If we denote an $n$-vector using the symbol $a$, the $i$ element of the vector $a$ is denoted $a_i$, where the subscript $i$ is an integer index that runs from $ to $n$, the size of the vector.

If two vectors $a$ and $b$ are *equal*, they have the same size and each of the corresponding entries are the same, we denote this by $a=b$, i.e. If $a$ and $b$ are $n$-vectors, then $a=b$ means $a_1=b_1, \ldots, a_n=b_n$.

The numbers or values of the elements in a vector are called *scalars*.

Vectors where the scalars are real numbers are referred to as *real vectors*. Likewise, if the scalars are complex numbers, we would refer to the vector as a *complex vector*. The set of all real numbers is written as $\mathbf{R}$, and the set of real $n$-vectors is denoted $\mathbf{R}^n$, so $a \in \mathbf{R}^n$ is another way to say that $a$ is an $n$-vector with real entries.

Notational conventions include:
- Greek letters $(\alpha, \beta, \ldots)$ for numbers,
- Lower-case letters $(a,x,f, \ldots)$ fo vectors,
- Bold font letters $(\mathbf{g})$ for vectors,
- Vectors written with arrows above them $(\vec{a})$.

![[8299.png]]
# 1 Vector Addition
Two vectors of the same size can be added together by adding the corresponding elements, to form another vector of the same size, called the sum of the vectors.
## 1.1 Addition example
$$
\left[ \; 
\begin{matrix} 
0 \\ 7 \\ 3
\end{matrix} 
\; \right]
+
\left[ \; 
\begin{matrix} 
1 \\ 2 \\ 0
\end{matrix} 
\; \right]
=
\left[ \; 
\begin{matrix} 
1 \\ 9 \\ 3
\end{matrix} 
\; \right]
$$
## 1.2 Subtraction example
$$
\left[ \; 
\begin{matrix} 
1 \\ 9
\end{matrix} 
\; \right]
-
\left[ \; 
\begin{matrix} 
1 \\ 1
\end{matrix} 
\; \right]
=
\left[ \; 
\begin{matrix} 
0 \\ 8
\end{matrix} 
\; \right]
$$
## 1.3 Properties
- Vector addition is *commutative*: $a+b=b+a$.
- Vector addition is associative: $(a+b)+c=a+(b+c)$. We can therefore write both as $a+b+c$.
![Proof that vector addition is commutative](28199.png)
# 2 Scalar-Vector Multiplication
Scalar multiplication or scalar-vector multiplication is where a vector is multiplied by a scalar, which is done by multiplying every element of the vector by the scalar.
$$
(-2) \left[ \; 
\begin{matrix} 
1 \\ 9 \\ 6
\end{matrix} 
\; \right] 
=
\left[ \; 
\begin{matrix} 
-2 \\ -18 \\ -12
\end{matrix} 
\; \right] 
\equiv
\left[ \; 
\begin{matrix} 
1 \\ 9 \\ 6
\end{matrix} 
\; \right] (-2)
=
\left[ \; 
\begin{matrix} 
-2 \\ -18 \\ -12
\end{matrix} 
\; \right] 
$$

# 3 Definitions
## 3.1 Block or Stacked Vectors
It can be useful to define vectors by *concatenating* or *stacking* two or more vectors, as in 
$$
a = \left[ \; 
\begin{matrix} 
b \\ c \\ d
\end{matrix} 
\; \right]
$$
where $a,b,c,$ and $d$ are vectors. If $b$ is an $m$-vector, $c$ is an $n$-vector, and $d$ is a $p$-vector, this defines the $(m+n+p)$-vector
$$
a=(b_1,b_2,\ldots,b_m,c_1,c_2,\ldots,c_n,d_1,d_2,\ldots,d_p).
$$
The stacked vector $a$ is also written as $a=(b,c,d)$. Stacked vectors can also include scalars (numbers). if $a$ is a 3-vector, $(1,a)$ is the 4-vector $(1,a_1,a_2,a_3)$.
## 3.2 Subvectors
In the equation 
$$
a=(b_1,b_2,\ldots,b_m,c_1,c_2,\ldots,c_n,d_1,d_2,\ldots,d_p)
$$
we say that $b,c,$ and $d$ are *subvectors* or *slices* of $a$, with sizes $m,n,$ and $p,$ respectively. *Colon notation* is used to denote subvectors.

If $a$ is a vector, then $a_{r:s}$ is the vector of size $s-r+1$, with entries $a_r, \ldots, a_s:$ 
$$
a_{r:s}=(a_r, \ldots, a_s).
$$
The subscript $r:s$ is called the *index range*.
### 3.2.1 Examples
If $z$ is the 4-vector $(1,-1,2,0)$, the slice $z_{2:3}$ is $z_2:3=(-1,2)$.
## 3.3 Zero Vectors
A *zero vector* is a vector with all elements equal to zero. Sometimes, the zero vector with size $n$ is written as $0_n$.
## 3.4 Unit Vectors
A (standard) unit vector is a vector with all elements equal to zero, except one element which is equal to one. The $i$th unit vector of size $n$ is the unit vector with $i$th element one, and denoted $e_i$. 
$$ 
\begin{align}
&e_1 = \left[ \; 
\begin{matrix} 
1 \\ 0 \\ 0
\end{matrix} 
\; \right],
&e_2 = \left[ \; 
\begin{matrix} 
0 \\ 1 \\ 0
\end{matrix} 
\; \right],
&&e_3 = \left[ \; 
\begin{matrix} 
0 \\ 0 \\ 1
\end{matrix} 
\; \right]
\end{align}
$$
we can describe the $i$th unit $n$-vector $e_i$ as
$$
(e_i)_j = 
\begin{cases}
1 & j = i \\ 
0 & j \neq i.
\end{cases}
$$
## 3.5 Ones Vectors
We use the notation $1_n$ for the $n$-vector with all its elements equal to one.
## 3.6 Sparsity
A vector is said to be sparse if many of its entries are zero; its sparsity pattern is the set of indices of nonzero entries. The number of nonzero entries of an $n$-vector $x$ is denoted $\mathbf{nnz}(x)$. 