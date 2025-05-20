# 1 Literature
Chapter 1, Section 2.1 + slides
# 2 Vectors
A vector is an ordered finite list of numbers. Vectors are usually written as vertical arrays, surrounded by square or curved brackets, as in
$$ 
\begin{pmatrix}
-1.1 \\ 0.0 \\ 3.6 \\ -7.2
\end{pmatrix}
\quad \text{or} \quad 
\begin{bmatrix}
-1.1 \\ 0.0 \\ 3.6 \\ -7.2
\end{bmatrix}
$$
They can also be written as numbers separated by commas and surrounded by parentheses as in
$$(-1.1, 0.0, 3.6, -7.2).$$
- An $n$-vector is a vector with $n$ elements
- The $i$th element in a vector is denoted by $a_i$
- Two vectors are equal $a=b$ if $a_1 = b_1, \dots, a_n=b_n$
- The numbers or values of elements in a vector are called scalars
- The set of all real $n$-vectors is denoted by $\mathbf{R}^n$, so $a \in \mathbf{R}^n$ is another way of saying that $a$ is a n $n$-vector with real entries.
## 2.1 Block or Stacked Vectors
A block vector or a stacked vector is a vector defined by concatenating or stacking two or more vectors as in
$$
a=
\begin{bmatrix} 
b \\ c \\ d
\end{bmatrix} 
$$
where $a,b,c$ and $d$ are vectors. If $b$ is an $m$-vector, $c$ is an $n$-vector and $d$ is a $p$-vector, this defines the $(m+n+p)$-vector
$$a=b_1,b_2,\dots,b_m,c_1,c_2,\dots,c_n,d_1,d_2,\dots,d_p)$$
The stacked vector $a$ is also written as $a=(b,c,d)$.
## 2.2 Subvectors
In the block vector mentioned before, $b,c,d$ would be subvectors or slices of $a$, with sizes $m,n,p$. Colon notation is used to denote subvectors. If $a$ is a vector, then $a_{r:s}$ is the vector of size $s-r+1$, with entries $a_r,\dots,a_s$
$$a_{r:s}=(a_r,\dots,a_s)$$
The subscript $r:s$ is called the index range.

If $z$ is the 4-vector $(1,-1,2,0)$, then $z_{2:3}=(-1,2)$.
## 2.3 Zero Vectors
A zero vector is a vector with all elements equal to zero. Sometimes it is written as $0_n$, but other times it is just written as $0$, where the size is determined from the context.
## 2.4 Unit Vectors
A unit vector is a vector with all elements equal to zero, except one element which is equal to one. The $i$th unit vector (of size $n$) is the unit vector with $i$the element on, and denoted $e_i$.
$$
\begin{aligned}
&e_1=\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}, &&e_2=\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}, &e_3\begin{bmatrix}0 \\ 0\\ 1\end{bmatrix}
\end{aligned}
$$
We can describe the $i$th unit $n$-vector $e_i$ as
$$
(e_i)_j = \begin{cases} 1 \quad j=i \\ 0 \quad j \neq i \end{cases}
$$
for $i,j=1,\dots,n$.
## 2.5 Ones Vector
We use the notation $\mathbf{1}_n$ for the $n$-vector with all its elements equal to one.
## 2.6 Sparsity
A vector is said to be sparse if many of its entries are zero. The number of the nonzero entries of an $n$-vector is denoted $\mathbf{nnz}(x)$.
# 3 Vector Addition
Two vectors of the same size can be added together by adding the corresponding elements, to form another vector of the same size, called the sum of the vectors.
$$
\begin{bmatrix}0 \\ 7 \\ 3\end{bmatrix} + \begin{bmatrix} 1 \\ 2 \\ 0 \end{bmatrix} = \begin{bmatrix}1 \\ 9 \\ 3\end{bmatrix}
$$
Vector subtraction is similar
$$
\begin{bmatrix}1 \\ 9\end{bmatrix} - \begin{bmatrix} 1 \\ 1\end{bmatrix} = \begin{bmatrix}0 \\ 8\end{bmatrix}
$$
## 3.1 Properties
- Vector addition is commutative: $a+b=b+a$
- Vector addition is associative: $(a+b)+c=a+(b+c)$. We can therefore write both as $a+b+c$.
- $a+0=0+a=a$. Adding the zero vector to a vector has no effect.
- $a-a=0$. Subtracting a vector from itself yields the zero vector.
# 4 Scalar-Vector Multiplication
Scalar multiplication or scalar-vector multiplication is an operation, in which a vector is multiplied by a scalar, which is done by multiplying every element of the vector by the scalar.
$$(-2)\begin{bmatrix}1 \\ 9 \\ 6\end{bmatrix}=\begin{bmatrix}-2 \\ -18 \\ -12\end{bmatrix}$$
Scalar-vector multiplication can also be written with the scalar on the right, as in
$$\begin{bmatrix}1 \\ 9 \\ 6\end{bmatrix}(1.5)=\begin{bmatrix}1.5 \\ 13.5 \\ 9\end{bmatrix}$$
## 4.1 Properties
- Commutative property: $\alpha a = a \alpha$
- Associative property: $(\beta \gamma)a=\beta(\gamma a)$.
- Left-distributive property: $(\beta + \gamma)a = \beta a + \gamma a$.
- Right-distributive property: $a(\beta + \gamma) = a\beta + a\gamma$.
- $\beta(a+b)=\beta a + \beta b$.
## 4.2 Linear Combinations
if $a_1, \dots, a_m$ are $n$-vectors, and $\beta_1, \dots, \beta_m$ are scalars, the $n$-vector
$$\beta_1 a_1 + \dots, \beta_m a_m$$
is called a linear combination of the vectors $a_1, \dots, a_n$. The scalars $\beta_1, \dots, \beta_m$ are called the coefficients of the linear combination.
## 4.3 Linear Combinations of Unit Vectors
We can write any $n$-vector $b$ as a linear combination of the standard unit vectors, as 
$$b=b_1e_1+\cdots+b_ne_n.$$
In this equation $b_i$ is the $i$th entry of $b$ (i.e., a scalar), and $e_i$ is the $i$th unit vector.
$$\begin{bmatrix}-1 \\ 3 \\ 5\end{bmatrix} = (-1)\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}+3\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}+5\begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix}.$$
## 4.4 Special Linear Combinations
### 4.4.1 The Sum of Vectors
The linear combination with $\beta_1=\cdots=\beta_m=1$, given by $a_1+\cdots + a_m$.
### 4.4.2 The Average of Vectors
$\beta_1=\cdots=\beta_m=1/m$, given by $(1/m)(a_1+\cdots+a_m)$. 
### 4.4.3 Affine Combination
When the coefficients sum to one, i.e., $\beta_1 + \cdots + \beta_m=1$. When the coefficients are nonnegative, it is called a convex combination, a mixture, or a weighted average. The coefficients in an affine or convex combination are sometimes given as percentages, which add up to $100\%$. 
# 5 Inner Product
The inner product (also called dot product) of two $n$-vectors is defined as the scalar
$$
a^Tb=a_1b_1+a_2b_2+\cdots+a_nb_n,
$$
the sum of the products of the corresponding entries.
$$
\begin{bmatrix}-1 \\ 2 \\ 2\end{bmatrix}^T\begin{bmatrix}1 \\ 0 \\ -3\end{bmatrix} = (-1)(1)+(2)(0)+(2)(-3)=-7
$$
When $n=1$, the inner product reduces to the usual product of two numbers.
## 5.1 Properties
- Commutative: $a^Tb=b^Ta$, the order of the two vector arguments in the inner product does not matter.
- Associativity with scalar multiplication: $(\gamma a)^Tb=\gamma(a^Tb)$, so we write both as $\gamma a^Tb$.
- Distributivity with vector addition: $(a+b)^Tc=a^Tc + b^Tc$. The inner product can be distributed across vector addition.
For any vectors $a,b,c,d$ of the same size, we have
$$(a+b)^T(c+d)=a^Tc+a^Td+b^Tc+b^d$$
## 5.2 General Examples
### 5.2.1 Unit Vector
$e^T_ia=a_i$. The inner product of a vector with the $i$th unit vector gives (or 'picks out') the $i$th element of $a$. 
### 5.2.2 Sum
$\mathbf{1}^Ta=a_1+\cdots+a_n$ The inner product of a vector with the vector of ones gives the sum of the elements of the vector.
### 5.2.3 Average
$(\mathbf{1}/n)^Ta=(a_1+\cdots+a_n)/n$. The inner product of an $n$-vector with the vector $\mathbf{1}/n$ gives the average or mean of the elements of the vector. The average of the entries of a vector is denoted by $\mathbf{avg} (x)$. The Greek letter $\mu$ is a traditional symbol used to denote the average or mean.
### 5.2.4 Sum of Squares
$a^Ta=a_1^2+\cdots + a_n^2$. The inner product of a vector with itself gives the sum of the squares of the elements of the vector.
### 5.2.5 Selective Sum
Let $b$ be a vector all of whose entries are either 0 or 1. Then $b^Ta$ is the sum of the elements in $a$ for which $b_i=1$.
## 5.3 Block Vectors
If the vectors $a$ and $b$ are block vectors, and the corresponding blocks have the same sizes (they conform), then we have
$$a^Tb=\begin{bmatrix}a_1 \\ \vdots \\ a_k\end{bmatrix}^T\begin{bmatrix}b_1 \\ \vdots \\ b_k\end{bmatrix}=a_1^Tb_1+ \cdots 0 a_k^Tb_k$$
The inner product of block vectors is the sum of the inner products of the blocks
# 6 Linear Functions
## 6.1 Function Notation
The notation $f:\mathbf{R}^n \to \mathbf{R}$ means that $f$ is a function that maps real $n$-vectors to real numbers, i.e.,it is a scalar-valued function of $n$-vectors. If $x$ is an $n$-vector, then $f(x)$, which is a scalar, denotes the value of the function $f$ at $x$. We can also interpret $f$ as a function of $n$ scalar arguments, the entries of the vector argument, in which case we write $f(x)$ as 
$$f(x)=f(x_1, x_2, \dots, x_n)$$
Here we refer to $x_1, \dots, x_n$ as the arguments of $f$. We sometimes say that $f$ is real-valued or scalar-valued, to emphasize that $f(x)$ is a real number or scalar.

To describe a function $f:\mathbf{R}^n \to \mathbf{R}$, we have to specify what its value is for any possible argument $x \in \mathbf{R}^n$. For example, we can define a function $f:\mathbf{R}^4 \to \mathbf{R}$ by $$f(x)=x_1+x_2-x_4^2$$
for any 4-vector $x$.
## 6.2 The Inner Product Function
Suppose $a$ is an $n$-vector. We can define a scalar-valued function $f$ of $n$-vectors, given by
$$f(x)=a^Tx=a_1x_1+a_2x_2+\cdots+a_nx_n$$
## 6.3 Superposition And Linearity
The inner product function $f$ satisfies the property
$$ 
\begin{align}
f(\alpha x + \beta y) &= a^T(\alpha x + \beta y) \\
&= a^T(\alpha x) + a^T(\beta y) \\
&= \alpha(a^Tx) + \beta(a^Ty) \\
&= \alpha f(x) + \beta f(y)
\end{align}
$$
for all $n$-vectors $x,y,$ and all scalars $\alpha, \beta$. This property is called superposition. A function that satisfies the superposition property is called linear. 

If a function $f$ is linear, superposition extends to linear combinations of any number of vectors, and not just linear combinations of two vectors: We have
$$f(\alpha_1x_1 + \cdots + \alpha_kx_k)=\alpha_af(x_1)+\cdots+\alpha_kf(x_k),$$
for any $n$-vectors $x_1,\dots,x_k$, and any scalars $\alpha_1, \dots, \alpha_k$. 

The superposition equality is sometimes broken down into two properties:
- Homogeneity: For any $n$-vector $x$ and any scalar $\alpha$, $f(\alpha x)=\alpha f(x)$.
- Additivity: For any $n$-vectors $x$ and $y$, $f(x+y)=f(x)+f(y)$. 
A function $f:\mathbf{R}^n \to \mathbf{R}$ is linear if it satisfies the two properties.

## 6.4 Inner Product Representation of a Linear Function
If a function is linear, then it can be expressed as the inner product of its argument with some fixed vector.
## 6.5 Affine Functions
A linear function plus a constant is called an affine function. A function $f:\mathbf{R}^n \to \mathbf{R}$ is affine if and only if it can be expressed as $f(x)=a^Tx+b$ for some $n$-vectors $a$ and scalar $b$, which is sometimes called the offset.

Any affine scalar-valued function satisfies the following variation on the superposition property:
$$f(\alpha x + \beta y)=\alpha f(x) + \beta f(y)$$
for all $n$-vectors $x,y$, and all scalars $\alpha, \beta$ that satisfy $\alpha+\beta=1$. For linear functions, superposition holds for any coefficients $\alpha$ and $\beta$; for affine functions, it holds when the coefficients sum to one (i.e., when the argument is an [[K01 - Introduction, Vectors, Linearity#4.4.3 Affine Combination|affine combination]]).

To see that the restricted superposition property holds for an affine function $f(x)=a^Tx+b$, we note that for any vectors $x,y$ and scalars $\alpha, \beta$ that satisfy $\alpha+\beta=1$,
$$ 
\begin{align}
f(\alpha x + \beta y) &= a^T(\alpha x + \beta y) + b \\
&= \alpha a^Tx+\beta a^Ty+(\alpha + \beta)b \\
&= alpha (a^Tx+b)+\beta(a^Ty+b) \\
&= \alpha f(x) + \beta f(y).
\end{align}
$$
(In the second line we use $\alpha + \beta = 1$.)

This restricted superposition property for affine functions is useful in showing that a function $f$ is not affine: We find vectors $x,y$ and numbers $\alpha, \beta$ with $\alpha + \beta = 1$, and verify that $f(\alpha x + \beta y) \neq \alpha f(x) + \beta f(y)$. This shows that $f$ cannot be affine.
