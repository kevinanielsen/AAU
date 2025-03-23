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
# 1 Vector Calculations
## 1.1 Vector addition
Two vectors of the same size can be added together by adding the corresponding elements, to form another vector of the same size, called the sum of the vectors.
## 1.2 Addition example
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
## 1.3 Subtraction example
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
## 1.4 Properties
- Vector addition is *commutative*: $a+b=b+a$.
- Vector addition is associative: $(a+b)+c=a+(b+c)$. We can therefore write both as $a+b+c$.
![Proof that vector addition is commutative](28199.png)
## 1.5 Scalar-Vector Multiplication
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
# 2 Linear Combinations
> A linear combination is when taking scaled versions of your vectors and adding them together.
![[73187.png]]

For vectors $a_1, \ldots, a_m$ and scalars $\beta_1, \ldots, \beta_m$,
$$
b_1 a_1 + \cdots + b_m a_m
$$
is a linear combination of the vectors, where $\beta_1, \ldots, \beta_m$ are the coefficients.

## 2.1 Linear Combinations of Unit Vectors
We can write any $n$-vector $b$ as a linear combination of the standard unit vectors, as
$$
b=b_1 e_1 + \cdots + b_n e_n.
$$
where $b_i$ is the $i$th entry of $b$ (i.e. a scalar), and $e_i$ is the $i$th unit vector.
In the linear combination of $e_1, \ldots, e_n$, the coefficients are the entries of the vector $b$.
### 2.1.1 Example
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
## 2.2 Special linear combinations
### 2.2.1 Sum
The linear combination with $\beta_1=\cdots = \beta_m = 1$ given by $a_1+\cdots + a_m$ is the sum of the vectors (since every vector has a coefficient of 1 and therefore the linear combination is just the addition of all the vectors).
### 2.2.2 Average
The linear combination with $\beta_1 = \cdots = \beta_m = 1 / m$, given by $(1/m)(a_1+ \cdots + a_m)$, is the *average* of the vectors.
### 2.2.3 Affine Combination
The linear combination where all the coefficients sum to one i.e. $\beta_1 + \cdots + \beta_m = 1$ is called an *affine combination*.

When the coefficients in an affine combination are nonnegative, it is called a *convex combination*, *mixture*, or a *weighted average*. 
# 3 Inner Products
The inner product of two $n$-vectors $a,b$ is defined as
$$
a^Tb=a_1b_1+a_2b_2+\cdots+a_nb_n
$$
The inner product of two vectors result in a scalar.

Other notation include $\langle a, b\rangle,(a \mid b), \ldots$

# 4 Linear Functions
## 4.1 Notation
A function mapping $n$-vectors to real numbers is denoted by
$f: \mathbf{R}^n \rightarrow \mathbf{R}$. i.e. it is a scalar-valued function of $n$-vectors. If $x$ is an $n$-vector, then $f(x)$, which is a scalar, denotes the *value* of the function $f$ at $x$. (In the notation $f(x)$, $x$ is referred to as the *argument* of the function). We can interpret $f$ as a function of $n$ scalar arguments, in which case we write $f(x)$ as 
$$f(x)=f(x_1, x_2, \dots, x_n).$$
## 4.2 The Inner Product Function
Suppose $a$ is an $n$-vector, then we could define a scalar-valued function $f$ of $n$-vectors, given by
$$f(x)=a^Tx=a_1x_1+a_2x_2+\cdots+a_nx_n$$
for any $n$-vector $x$, this function gives the inner product of its $n$-vector argument $x$ with some (fixed) $n$-vector $a$. 
## 4.3 Superposition and Linearity
$f$ satisfies the superposition property if
$$
f(\alpha x + \beta y)= \alpha f(x) + \beta f(y)
$$
holds for all numbers $\alpha, \beta,$ and all $n$-vectors, $x,y$.

Any function that satisfies superposition is called *linear*.

Linear functions always cross through $(0,0)$

The superposition equality can be broken down into two properties:
Homogeneity: For any $n$-vector $x$ and any scalar $\alpha$, $f(\alpha x)=\alpha f(x)$.
Additivity: For any $n$-vectors $x$ and $y$, $f(x+y)=f(x)+f(y)$.

Any linear scalar-valued function $f$ can be described as the inner product of its argument with some fixed vector.
## Affine functions
A linear function plus a constant is called an affine function. A function $f:\mathbf{R}^n \rightarrow \mathbf{R}$ is affine if and only if it can be expressed as $f(x)=a^Tx+b$ for some $n$-vector $a$ and scalar $b$, which is sometimes called the *offset*. For example, the function on 3-vectors defined by
$$
f(x)=2.3-2x_1+1.3x_2-x_3
$$
is affine, with $b=2.3,a=(-2,1.3,-1)$.

Any affine scalar-valued function satisfies the following variation on the super-position property:
$$
f(\alpha x + \beta y)=\alpha f(x) + \beta f(y),
$$
for all $n$-vectors $x,y$, and all scalars $\alpha, \beta$ that satisfy $\alpha + \beta = 1$, i.e., for linear functions, superposition holds for any coefficients $\alpha$ and $\beta$; for affine functions, it holds when the coefficients sum to one. 

To see that the restricted superposition property holds for an affine function $f(x)=a^T x + b$, we note that, for any vectors $x,y$ and scalars $\alpha$ and $\beta$ that satisfy $\alpha + \beta = 1$, 
$$ 
\begin{align}
f(\alpha x + \beta y) &= a^T(\alpha x + \beta y) + b \\
&= \alpha a^Tx + \beta a^Ty+(\alpha + \beta)b \\
&= \alpha (a^Tx + b)+\beta(a^Ty+b) \\
&= \alpha f(x) + \beta f(y).
\end{align}
$$
To show that a function is not affine, we find vectors $x,y$ and numbers $\alpha, \beta$ with $\alpha+\beta=1$, and verify that $f(\alpha x + \beta y) \neq \alpha f(x)+\beta f(y)$. This shows that $f$ cannot be affine. The converse is also true: Any  scalar-valued function that satisfies the restricted superposition property is affine
# 6 Norms
## 6.1 Euclidean Norm
The euclidean norm of a vector is the squareroot of the sum of the squares of its elements i.e. $\lVert x \rVert = \sqrt{x^2_1 + x^2_2 + \cdots + x^2_n}$. The euclidean norm can also be expressed as the squareroot of the inner product of the vector itself i.e. $\lVert x \rVert = \sqrt{x^Tx}$. We should avoid expressing it as the length of the vector as that usually refers to the dimension of the vector. When $x$ is a scalar or a 1-vector, the norm is the same as the absolute value of $x$.
### 6.1.1 Properties of norm
#### 6.1.1.1 Nonnegative homogeneity 
$\lVert \beta x \rVert = \lvert \beta \rvert \lVert x \rVert$. Multiplying a vector by a scalar multiplies the norm by the absolute value of the vector.
#### 6.1.1.2 Triangle inequality
$\lVert x + y \rVert \leq \lVert x \rVert + \lVert y \rVert$. The euclidean norm of a sum of two vectors is no more than the sum of their norms. Another name is *subadditivity*.
#### 6.1.1.3 Nonnegativity
$\lVert x \rVert \geq 0$.
#### 6.1.1.4 Definiteness
$\lVert x \rVert = 0$ only if $x = 0$.
## 6.2 Root Mean Square (RMS)
The root mean square value of a vector $x$ is defined by 
$$
\mathbf{rms}(x)=\sqrt{\dfrac{x_1^2+\cdots+x_n^2}{n}}=\dfrac{\lVert x \rVert}{\sqrt{n}}
$$
The argument of the square root in the middle statement $\dfrac{x_1^2+\cdots+x_n^2}{n}$ is called the mean square value of $x$ and is denoted by $\mathbf{ms}(x)$. 

The rms tells us what the 'typical' value of $\lvert x_i \rvert$ is. For example, the norm of the vector with only ones would be $\sqrt{n}$, while the RMS value would be 1 independent of $n$.
## 6.3 Norm of a sum
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
## 6.4 Norm of block vectors
The norm-squared of a stacked vector is the sum of the norm-squared values of its subvectors.
### 6.4.1 Example
With $d=(a,b,c)$ where $a, b, c$ are vectors, we have
$$
\lVert d \rVert ^2 = d^T d = a^T a + b^T b + c^T c = \lVert a \rVert^2 + \lVert b \rVert^2 + \lVert c \rVert^2.
$$
The reverse would be to express the sum of the norm-squared values of some vectors as the norm-square value of a block vector formed from them. We can write the equality above in terms of norms as
$$
\lVert (a,b,c) \rVert = \sqrt{\lVert a \rVert^2+\lVert b \rVert^2+\lVert c \rVert^2}=\lVert (\lVert a \rVert, \lVert b \rVert, \lVert c \rVert) \rVert.
$$
I.e. the norm of a stacked vector is the norm of the vector formed from the norms of the subvectors.
## 6.5 Chebyshev inequality
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
# 7 Standard deviation
For any vector $x$, the vector $\tilde{x} = x - \mathbf{avg} (x) \mathbf 1$ is called the associated de-meaned vector, obtained by subtracting from each entry of $x$ the mean value of the entries. The mean value of the entries of $\tilde x$ is zero, i.e., $\mathbf{avg}(\tilde x)=0$. De-meaned version of $x$ is $x$ with its mean removed. It is used to understand how entries of a vector deviate from their mean value. It is zero if all the entries in the original vector $x$ are the same.

The standard deviation of an $n$-vector $x$ is defined as the RMS value of the de-meaned vector $x-\mathbf{avg}(x)\mathbf 1$, i.e.,
$$
\mathbf{std}(x)=\sqrt{\dfrac{(x_1-\mathbf{avg}(x))^2+\cdots + (x_n-\mathbf{avg}(x))^2}{n}}.
$$
This is the same as the RMS deviation between a vector $x$ and the vector all of whose entries are $\mathbf{avg}(x)$. It can be written using the inner product and norm as 
$$
\mathbf{std}(x)=\dfrac{\lVert x - (\mathbf{1}^Tx/n)\mathbf 1 \lVert}{\sqrt n}.
$$
Where $\mathbf{1}$ denotes an $n$-vector where all values are 1, therefore $\mathbf{1}^T x$ denotes the sum of the entries of the vector $x$.

This tells us the typical amount by which the entries of $x$ deviate from their average value. It is zero only if all entries are equal. The standard deviation of a vector is small when the entries of the vector are nearly the same.

The greek letter $\sigma$ may be used to denote standard deviation, while the mean can be denoted by $\mu$ (mu).

$$
\mathbf{rms}(x)^2 = \mathbf{avg}(x)^2 + \mathbf{std}(x)^2
$$
## 7.1 Example
$$ 
\begin{align}
x &= (1,-2,3,2) \\
\mathbf{avg}(x) &= 1 \\
\tilde x &= (0,-3,2,1) \\
\mathbf{std}(x) &= 1.872
\end{align}
$$
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


# 9 Angle
## 9.1 Cauchy-Schwarz Inequality
$$
\lvert a^T b \rvert \leq \lVert a \rVert \cdot \lVert b \rVert
$$
for any $n$-vectors $a$ and $b$.
## 9.2 Angle between two vectors
The angle between two nonzero vectors $a, b$ is defined as 
$$
\theta = \arccos \left( \dfrac{a^T b}{\Vert a \Vert \Vert b \Vert} \right)
$$
where arccos denotes the inverse cosine, normalized to lie between the interval $[0, \pi]$. In other words, we define $\theta$ as the unique number to lie between $0$ and $\pi$ that satisfies
$$
a^T b = \Vert a \Vert \Vert b \Vert \cos 0.
$$
The angle between $a$ and $b$ is written as $\angle (a,b)$, and is sometimes expressed in degrees.

- If the angle is $\pi / 2 = 90 ^ \circ$ i.e. $a^T b = 0$ the vectors are said to be orthogonal and denoted by $a \perp b$. By convention we say that a zero vector is orthogonal to any vector.
- If the angle is zero, i.e., $a^T b = \lVert a \lVert \lVert b \lVert$, the vectors are aligned.
- If the angle is $\pi = 180 ^\circ$, i.e., $a^T b = -\lVert a \lVert \lVert b \lVert$, the vectors are anti-aligned.
- If $\angle (a,b) < \pi / 2 = 90 ^\circ$, the vectors are said to make an acute angle. This is the same as $a^T b > 0$ i.e. the vectors have a positive inner product.
- If $\angle (a,b) > \pi / 2 = 90^ \circ$, the vectors have an obtuse angle. This is the same as $a^T b < 0$, i.e., the vectors have a negative inner product.
### 9.2.1 Example
The angle between vectors $a=(1,2,-1)$ and $b=(2,0,-3)$ is 
$$
\arccos \left( \dfrac{5}{\sqrt{6} \sqrt{13}} \right) = \arccos (0.5661) = 0.9690=55.52^ \circ
$$
## 9.3 Correlation coefficient
Assuming the de-meaned vectors $\tilde a, \tilde b$ are not zero, we define their correlation coefficient as
$$
\rho = \dfrac{\tilde a ^T \tilde b}{\lVert \tilde a \lVert \lVert \tilde b \lVert}.
$$
$\rho = \cos \theta$, where $\theta = \angle (\tilde a, \tilde b)$. The correlation coefficient can be expressed in terms of the vectors $u$ and $v$ obtained by standardizing $a$ and $b$. With $u=\tilde a / \mathbf{std}(a)$ and $v=\tilde b / \mathbf{std}(b)$, we have
$$
\rho = u^T v /n
$$
The Cauchy-Schwarz inequality tells us that the correlation coefficient ranges between -1 and +1. It is sometimes expressed as a percentage.

When $\rho = 0$ or $\rho = 0\%$, we say the vectors are uncorrelated. By convention, we say that a vector with all entries equal is uncorrelated with any vector.

High correlation (say, $\rho = 0.8 = 80\%$) means that the entries of $a$ and $b$ are typically above their mean for many of the same entries. $\rho = 1$ only occurs if $\tilde a$ and $\tilde b$ are aligned. $\rho = -1$ occurs only when $\tilde a$ and $\tilde b$ are negative multiples of each other.
![[64062.png]]
# 10 Linear Dependence
A set of $n$-vectors $\{a_1, \ldots, a_k\}$ (with $k \geq 1$) is linearly dependent if
$$
\beta_1a_1 + \cdots + \beta_k a_k = 0
$$
holds for some $\beta_1, \ldots, \beta_k$, that are not all zero. If any vector in the set is a 0-vector (a vector where all values are 0), the set is linearly dependent. If a set of vectors is linearly dependent it means that at least one of the vectors in the set can be written as a linear combination of the others.
### 10.1.1 Example
$$ 
a_1 = \left[ \; 
\begin{matrix} 
0.2 \\ -7 \\ 8.6
\end{matrix} 
\; \right], 
\quad
a_2 = \left[ \; 
\begin{matrix} 
-0.1 \\ 2 \\ -1
\end{matrix} 
\; \right],
\quad
a_3 = \left[ \; 
\begin{matrix} 
0 \\ -1 \\ 2.2
\end{matrix} 
\; \right]
$$
are all linearly dependent, since $a_1+2a_2+(-3)a_3=0$ (since not all scalars/weights are 0).

We can express any of them as linear combinations of the other two e.g.
$$a_2 = (-1/2)a_1+(3/2)a_3$$
![[7300.png]]

## 10.2 Linear independence

A set of $n$-vectors $\{a_1, \ldots, a_k\}$ (with $k \geq 1$) is linearly independent if
$$
\beta_1a_1 + \cdots + \beta_k a_k = 0
$$
only holds for $\beta_1 = \cdots = \beta_k = 0$.

### 10.2.1 Independence-dimension inequality
If the n-vectors $a_1, \ldots, a_k$ are linearly independent, then $k \leq n$. In words: A linearly independent collection of $n$-vectors can have at most n elements.
In other words, any collection of $n+1$ or more $n$-vectors are linearly dependent.
## 10.3 Basis
A collection of $n$ linear independent $n$-vectors $_1, \ldots, a_n$, i.e. the biggest possible collection of linearly independent vectors, is called a *basis*. Any $n$-vector $b$ can be expressed as a linear combination of them by the [[Vectors#11.3.1 Independence-dimension inequality|independence-dimension inequality]]
$$b = \beta_1a_1 + \cdots + \beta_na_n$$
for some $\beta_1, \ldots, \beta_n$.
### 10.3.1 Expansion
When we refer to the $n$-vector $b$, as a linear combination of a basis $a_1, \ldots, a_n$, we refer to 
$$
b = \alpha_1a_1 + \ldots + \alpha_n a_n,
$$
as the *expansion* of $b$ in the $a_1, \ldots, a_n$ basis. The numbers $\alpha_1, \ldots, \alpha_n$ are called the *coefficients* of the expansion of $b$ in the basis $a_1, \ldots, a_n$.
## 10.4 Orthonormal vectors
A collection of $n$-vectors $a_1, \ldots, a_k$ are (mutually) orthogonal if $a_i \perp a_j$ for any $i,j$ with $i \neq j$.
A collection of vectors $a_1, \ldots, a_k$ is *orthonormal* if it is orthogonal and $\lVert a_i \rVert = 1$ for $i=1, \ldots, k$. (A vector of norm 1 is called *normalized*, dividing a vector by it's norm is called *normalizing* it). Therefore, each vector in an orthonormal collection of vectors is normalized, and two different vectors from the collection are orthogonal. These conditions can combined into a statement about the inner product of pairs of vectors in a collection $a_1, \ldots, a_k$ is orthonormal means that
$$
a_i^T a_j= \begin{cases}1 & i=j \\ 0 & i \neq j\end{cases}
$$
Orthonormal collections of vectors are linearly independent.

Orthonormality is an attribute of a collection or set of vectors and not an attribute of a vector itself. 
### 10.4.1 Linear Combinations of Orthonormal Vectors
Suppose a vector $x$ is a linear combination of $a_1, \ldots, a_k$, where $a_1, \ldots, a_k$ are orthonormal,
$$x = \beta_1 a_1 + \cdots + \beta_k a_k,$$
taking the inner product of both sides of the equation with $a_i$ yields
$$
a_i^T x = a_i^T(\beta_1 a_1 + \cdots + \beta_k a_k)=\beta_i,
$$
so by taking the inner product the inner products with the vectors we can easily find the coefficients of the linear combination. 

For any $x$ that is a linear combination of orthonormal vectors $a_1, \ldots, a_k$, we have the identity
$$
x = (a_1^Tx)a_1+\cdots + (a_k^Tx)a_k.
$$
This identity gives a simple way to check if a $n$-vector $y$ is a linear combination of the orthonormal vectors $a_1, \ldots, a_k$. If the identity holds for $y$, i.e.
$$
y = (a_1^Ty)a_1+\cdots + (a_k^Ty)a_k.
$$
then $y$ is a linear combination of $a_1, \ldots, a_k$. Conversely, if $y$ is a linear combination of $a_1, \ldots, a_k$, then the identity holds for $y$.
### 10.4.2 Orthonormal Basis
If the $n$-vectors $a_1, \ldots, a_k$ are orthonormal, they are linearly independent, and therefore also a [[Vectors#11.3 Basis|basis]]. This is called an *orthonormal basis*.
## 10.5 Gram-Schmidt (orthogonalization) algorithm
An algorithm to check if $a_1, \ldots, a_k$ are linearly independent.

![[31584.png]]

- if the algorithm stops early in iteration $i= j$ (step 2), then $a_j$ is a linear combination of $a_1,\ldots,a_j−1$ (so $a_1,\ldots,a_k$ are linearly dependent).
- If the Gram-Schmidt algorithm completes, then the set of vectors are linearly independent.

The orthogonalization step reduces to $\tilde{q}_1=a_1$ when $i=1$. If the algorithm dos not quit in step 2, i.e., $\tilde q_1, \ldots, \tilde q_k$  are all nonzero, and we can conclud that the original collection of vectors is linearly independent, likewise if the algorithm dos quit early, we can conclude that the original collection of vectors is linearly dependent (and that $a_j$ is a linear combination of $a_1, \ldots, a_{j-1}$).
### 10.5.1 Determining if a vector is a linear combination of linearly independent vectors
If vectors $a_1, \ldots, a_k$ are linearly independent, we can determine if a vector $b$ is a linear combination of them using the Gram-Schmidt algorithm. We apply the algorithm to the list of $k+1$ vectors
$$
a_1, \ldots, a_k, b
$$
These vectors are linearly dependent if $b$ is a linear combination of $a_1, \ldots, a_k$. 
# 11 Definitions
## 11.1 Block or Stacked Vectors
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
## 11.2 Subvectors
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
### 11.2.1 Examples
If $z$ is the 4-vector $(1,-1,2,0)$, the slice $z_{2:3}$ is $z_{2:3}=(-1,2)$.
## 11.3 Zero Vectors
A *zero vector* is a vector with all elements equal to zero. Sometimes, the zero vector with size $n$ is written as $0_n$.
## 11.4 Unit Vectors
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
## 11.5 Ones Vectors
We use the notation $1_n$ for the $n$-vector with all its elements equal to one.
## 11.6 Sparsity
A vector is said to be sparse if many of its entries are zero; its sparsity pattern is the set of indices of nonzero entries. The number of nonzero entries of an $n$-vector $x$ is denoted $\mathbf{nnz}(x)$. 
## 11.7 Flops
Basic arithmetic operations (addition, multiplication, $\ldots$) are called floating point operations or flops.

The complexity of an algorithm or operation can be defined by the total number of flops needed. This is usually very grossly approximated.
