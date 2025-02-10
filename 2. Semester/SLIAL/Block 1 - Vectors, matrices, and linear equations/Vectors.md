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
![[72003.png]]
# 3 Linear Combinations
> A linear combination is when taking scaled versions of your vectors and adding them together.
![[73187.png]]

For vectors $a_1, \ldots, a_m$ and scalars $\beta_1, \ldots, \beta_m$,
$$
b_1 a_1 + \cdots + b_m a_m
$$
is a linear combination of the vectors, where $\beta_1, \ldots, \beta_m$ are the coefficients.

## 3.1 Linear Combinations of Unit Vectors
We can write any $n$-vector $b$ as a linear combination of the standard unit vectors, as
$$
b=b_1 e_1 + \cdots + b_n e_n.
$$
where $b_i$ is the $i$th entry of $b$ (i.e. a scalar), and $e_i$ is the $i$th unit vector.
In the linear combination of $e_1, \ldots, e_n$, the coefficients are the entries of the vector $b$.
### 3.1.1 Example
$$
\left[ \; 
\begin{matrix} 
-1 \\ 3 \\ 5
\end{matrix} 
\; \right]
=
(-1)
\left[ \; 
\begin{matrix} 
1 \\ 0 \\ 0
\end{matrix} 
\; \right]
+
3
\left[ \; 
\begin{matrix} 
0 \\ 1 \\ 0
\end{matrix} 
\; \right]
+
5\left[ \; 
\begin{matrix} 
0 \\ 0 \\ 1
\end{matrix} 
\; \right]
$$
## 3.2 Special linear combinations
### 3.2.1 Sum
The linear combination with $\beta_1=\cdots = \beta_m = 1$ given by $a_1+\cdots + a_m$ is the sum of the vectors (since every vector has a coefficient of 1 and therefore the linear combination is just the addition of all the vectors).
### 3.2.2 Average
The linear combination with $\beta_1 = \cdots = \beta_m = 1 / m$, given by $(1/m)(a_1+ \cdots + a_m)$, is the *average* of the vectors.
### 3.2.3 Affine Combination
The linear combination where all the coefficients sum to one i.e. $\beta_1 + \cdots + \beta_m = 1$ is called an *affine combination*.

When the coefficients in an affine combination are nonnegative, it is called a *convex combination*, *mixture*, or a *weighted average*. 
# 4 Inner Products
The inner product of two $n$-vectors $a,b$ is defined as
$$
a^Tb=a_1b_1+a_2b_2+\cdots+a_nb_n
$$
The inner product of two vectors result in a scalar.

Other notation include $\langle a, b\rangle,(a \mid b), \ldots$

# 5 Linear Functions
A function mapping $n$-vectors to numbers is denoted by
$f: \mathbf{R}^n \rightarrow \mathbf{R}$. 

$f$ satisfies the superposition property if
$$
f(\alpha x + \beta y)= \alpha f(x) + \beta f(y)
$$
holds for all numbers $\alpha, \beta,$ and all $n$-vectors, $x,y$.

Any function that satisfies superposition is called linear.

Linear functions always cross through $(0,0)$

# 6 Regression Models
Regression model is the affine function of $x$
$$
\hat{y} = x^T \beta + v
$$
where: 
- $x$ is a feature vector; its elements $x_i$ are called regressors,
- $n$-vector $\beta$ is the weight vector,
- the scalar $v$ is the offset,
- the scalar $\hat{y}$ is the prediction.

## 6.1 Example
$$
\left[ \; 
\begin{matrix} 
1 \\ 2 \\ 3
\end{matrix} 
\; \right]
\left[ \; 
\begin{matrix} 
0 \\ -1 \\ 4
\end{matrix} 
\; \right]=1\cdot0+2\cdot-1+3\cdot4=10
$$
# 7 Norms
## 7.1 Euclidean Norm
The euclidean norm of a vector is the squareroot of the sum of the squares of its elements i.e. $\lVert x \rVert = \sqrt{x^2_1 + x^2_2 + \cdots + x^2_n}$. The euclidean norm can also be expressed as the squareroot of the inner product of the vector itself i.e. $\lVert x \rVert = \sqrt{x^Tx}$. We should avoid expressing it as the length of the vector as that usually refers to the dimension of the vector. When $x$ is a scalar or a 1-vector, the norm is the same as the absolute value of $x$.
### 7.1.1 Properties of norm
#### 7.1.1.1 Nonnegative homogeneity 
$\lVert \beta x \rVert = \lvert \beta \rvert \lVert x \rVert$. Multiplying a vector by a scalar multiplies the norm by the absolute value of the vector.
#### 7.1.1.2 Triangle inequality
$\lVert x + y \rVert \leq \lVert x \rVert + \lVert y \rVert$. The euclidean norm of a sum of two vectors is no more than the sum of their norms. Another name is *subadditivity*.
#### 7.1.1.3 Nonnegativity
$\lVert x \rVert \geq 0$.
#### 7.1.1.4 Definiteness
$\lVert x \rVert = 0$ only if $x = 0$.
## 7.2 Root Mean Square (RMS)
The root mean square value of a vector $x$ is defined by 
$$
\mathbf{rms}(x)=\sqrt{\dfrac{x_1^2+\cdots+x_n^2}{n}}=\dfrac{\lVert x \rVert}{\sqrt{n}}
$$
The argument of the square root in the middle statement $\dfrac{x_1^2+\cdots+x_n^2}{n}$ is called the mean square value of $x$ and is denoted by $\mathbf{ms}(x)$. 

The rms tells us what the 'typical' value of $\lvert x_i \rvert$ is. For example, the norm of the vector with only ones would be $\sqrt{n}$, while the RMS value would be 1 independent of $n$.
## 7.3 Norm of a sum
Calculating the norm of a sum of two vectors can be done with the following formula:
$$
\lVert x+y \rVert = \sqrt{\lVert x \rVert ^2 + 2x^T y + \lVert y \rVert^2}.
$$
Deriving this formula can be done in the following way:
$$ 
\begin{align}
\lVert x + y \rVert^2 &= (x+y)^T(x+y) \\
&= x^Tx+x^Ty+y^Tx+y^Ty \\
&= \lVert x \rVert ^2 + 2x^Ty + \lVert y \rVert ^2.
\end{align}
$$
Taking the squareroot of both sides of the equation yields the formula above.
## 7.4 Norm of block vectors
The norm-squared of a stacked vector is the sum of the norm-squared values of its subvectors.
### 7.4.1 Example
With $d=(a,b,c)$ where $a, b, c$ are vectors, we have
$$
\lVert d \rVert ^2 = d^T d = a^T a + b^T b + c^T c = \lVert a \rVert^2 + \lVert b \rVert^2 + \lVert c \rVert^2.
$$
The reverse would be to express the sum of the norm-squared values of some vectors as the norm-square value of a block vector formed from them. We can write the equality above in terms of norms as
$$
\lVert (a,b,c) \rVert = \sqrt{\lVert a \rVert^2+\lVert b \rVert^2+\lVert c \rVert^2}=\lVert (\lVert a \rVert, \lVert b \rVert, \lVert c \rVert) \rVert.
$$
I.e. the norm of a stacked vector is the norm of the vector formed from the norms of the subvectors.
## 7.5 Chebyshev inequality
Suppose that $x$ is an $n$-vector, and that $k$ of its entries satisfy $\lVert x_i \rVert \geq a$, where $a > 0$. Then $k$ of its entries satisfy $x_i^2 \geq a^2$. It follows that
$$
\lVert x \rVert^2=x_1+^2+\cdots + x_n^2 \geq ka^2,
$$
since $k$ of the numbers in the sum are at least $a^2$, and the other $n-k$ numbers are nonnegative. We can conclude that $k \leq \lVert x \rVert^2 / a^2$, which is called the *Chebyshev inequality*. When $n \leq \lVert x \rVert^2 / a^2$, the inequality tells us nothing, since we always have $k \leq n$.

For $a > \lVert x \rVert$, the inequality is $k \leq \lVert x \rVert^2 / a^2 < 1$, so we conclude that $k = 0$ since $k$ is an integer. In other words, no entry of a vector can be larger in magnitude than the norm of the vector. It can be written in terms of the RMS value of a vector
$$
\dfrac{k}{n} \leq \left(\dfrac{\mathbf{rms}(x)}{a}\right)^2,
$$
where $k$ is, as above, the number of entries of $x$ with an absolute value of at least $a$. It says for example that no more than $1/25=4\%$ of the entries of a vector can exceed its RMS value by more than a factor of 5. 
# 8 Distance
## 8.1 Euclidean distance
![[195.png]]
We can use the norm to define the *Euclidean distance* between two vectors $a$ and $b$ as the norm of their difference
$$
\mathbf{dist}(a,b)=\lVert a-b \rVert.
$$
The euclidean distance is defined for vectors of any dimension; we can refer to the distance between two vectors of dimension 100. 

If $a$ and $b$ are $n$-vectors, we refer to the RMS value of the difference, $\lVert a - b \rVert / \sqrt{n}$, as the *RMS deviation* between two vectors.
## 8.2 Triangle inequality
Geometric intuition tells us that the length of any side of a triangle cannot exceed the sum of the lengths of the other two sides. For example we have
$$
\lVert a - c \rVert \leq \lVert a - b \rVert + \lVert b - c \rVert
$$
i.e. the sum of the length of sides a->b and b->c will always be greater than the length of side a->c.
$$
\lVert a - c \rVert = \lVert (a - b) + (b - c) \rVert \leq \lVert a - b \rVert + \lVert b - c \rVert
$$
# 9 Definitions
## 9.1 Block or Stacked Vectors
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
## 9.2 Subvectors
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
### 9.2.1 Examples
If $z$ is the 4-vector $(1,-1,2,0)$, the slice $z_{2:3}$ is $z_{2:3}=(-1,2)$.
## 9.3 Zero Vectors
A *zero vector* is a vector with all elements equal to zero. Sometimes, the zero vector with size $n$ is written as $0_n$.
## 9.4 Unit Vectors
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
## 9.5 Ones Vectors
We use the notation $1_n$ for the $n$-vector with all its elements equal to one.
## 9.6 Sparsity
A vector is said to be sparse if many of its entries are zero; its sparsity pattern is the set of indices of nonzero entries. The number of nonzero entries of an $n$-vector $x$ is denoted $\mathbf{nnz}(x)$. 
## 9.7 Flops
Basic arithmetic operations (addition, multiplication, $\ldots$) are called floating point operations or flops.

The complexity of an algorithm or operation can be defined by the total number of flops needed. This is usually very grossly approximated.