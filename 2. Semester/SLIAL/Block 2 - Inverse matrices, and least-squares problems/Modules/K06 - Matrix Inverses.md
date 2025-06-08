# 1 Literature
Chapter 11 + Slides
# 2 Left and Right Inverses
Recall that for a number $a$, its (multiplicative) inverse is the number $x$ for which $xa=1$, which we usually denote as $x=1/a$ or $x=a^{-1}$. 
## 2.1 Left Inverse
A matrix $X$ that satisfies
$$XA=I$$
is called a left inverse of $A$. The matrix $A$ is said to be left-invertible if a left inverse exists. Note, that if $A$ has size $m \times n$, a left inverse $X$ will have size $n \times m$, the same dimensions as $A^T$.
### 2.1.1 Example
The matrix
$$
A = \begin{bmatrix*}[r]
-3 & -4 \\ 4 & 6 \\ 1 & 1
\end{bmatrix*}
$$
has two different left inverses:
$$
B=\frac19 \begin{bmatrix*}[r]
-11 & -10 & 16 \\ 
7 & 8 & -11
\end{bmatrix*}, \quad C = \frac12 \begin{bmatrix*}[r]
0 & -1 & 6 \\
0 & 1 & -4
\end{bmatrix*}.
$$
Which we can confirm by checking $BA=CA=I$:
$$
BA = 
\frac19 \begin{bmatrix*}[r]
-11(-3) + (-10)(4) + 16(1) & -11(-4)+(-10)(6)+16(1) \\
7(-3)+8(4)+(-11)(1) & 7(-4)+8(6)+(-11)(1)
\end{bmatrix*} = \begin{bmatrix*}[r]
1 & 0 \\ 0 & 1
\end{bmatrix*}=I
$$
$$
CA = \frac12 \begin{bmatrix*}[r]
0(-3)+(-1)(4)+6(1) & 0(-4)+(-1)(6)+6(1) \\
0(-3)+1(4)+(-4)(1) & 0(-4)+1(6)+(-4)(1)
\end{bmatrix*} = \begin{bmatrix*}[r]
1 & 0 \\ 0 & 1
\end{bmatrix*}=I
$$

A matrix with orthonormal columns satisfies $A^TA=I$, so it is left-invertible; its transpose $A^T$ is a left inverse.

## 2.2 Left-Invertibility and Column Independence
If $A$ has a left inverse $C$ then the columns of $A$ are [[K02 - Linear Independence|linearly independent]].
To see this, suppose that $Ax=0$
$$
0=C(Ax)=(CA)x=Ix=x
$$
## 2.3 Dimensions of Left Inverses
Suppose the $m \times n$ matrix $A$ is wide. By the [[K02 - Linear Independence#3.1 Independence-Dimension Inequality|independence-dimension inequality]], its columns are linearly dependent, and therefore it is not left-invertible. **Only square or tall matrices can be left-invertible.**
## 2.4 Solving Linear Equations With a Left Inverse
Suppose that $Ax=b$, where $A$ is an $m \times n$ matrix and $x$ is an $n$-vector. If $C$ is a left inverse of $A$, we have
$$
Cb=C(Ax)=(CA)x=Ix=x,
$$
which means that $x=Cb$ is a solution of the set of linear equations. The columns of $A$ are linearly independent (since it has a left inverse), so there is only one solution of the linear equations $Ax=b$, i.e., $x=Cb$ is the solution of $Ax=b$. 

If there is no $x$ that satisfies the linear equations $Ax=b$ and $C$ is a left inverse of $A$. Then $x=Cb$ does not satisfy $Ax=b$, since no vector satisfies this equation by assumption. This gives a way to find a solution to linear equations when there is one, provided we have a left inverse of $A$. We simply test whether $A(Cb)=b$. If this holds, then we have found a solution of the linear equations; if it doesn't, then we can conclude there is no solution of $Ax=b$.
## 2.5 Right Inverse
A matrix $X$ that satisfies
$$AX=I$$
Is called a right inverse of $A$. The matrix $A$ is right-invertible if a right inverse exists. Any right inverse has the same dimensions as $A^T$. 
## 2.6 Left and Right Inverse of Matrix Transpose
If $A$ has a right inverse $B$, then $B^T$ is a left inverse of $A^T$, since $B^TA^T=(AB)^T=I$. 
- A matrix is right-invertible if and only if its rows are linearly independent.
- A tall matrix cannot have a right inverse. Only square or wide matrices can be right-invertible.
## 2.7 Solving Linear Equations With a Right Inverse
Consider the set of $m$ linear equations in $n$ variables $Ax=b$. Suppose $A$ is right-invertible, with right inverse $B$. This implies that $A$ is square or wide, so lienar equations $Ax=b$ are square or under-determined.

Then, for any $m$-vector $b$, the $n$-vector $x=Bb$ satisfies the equation $Ax=b$. 

In summary, a right inverse can be used to find a solution of a square or under-determined set of linear equations, for any vector $b$.
# 3 Inverse
If a matrix is left- and right-invertible, then the left and right inverses are unique and equal. To see this, suppose that $AX=I$ and $YA=I$, i.e., $X$ is any right inverse and $Y$ is any left inverse of $A$. Then we have
$$
X=(YA)X=Y(AX)=Y,
$$
i.e., any left inverse of $A$ is equal to any right inverse of $A$. 

When a matrix is both right- and left-invertible, it is denoted as $A^{-1}$ and called invertible or nonsingular. A square matrix that is not invertible is called singular.

## 3.1 Dimensions of Invertible Matrices
Invertible matrices must be square.
## 3.2 Solving Linear Equations With the Inverse
Consider the square system of $n$ linear equations with $n$ variables, $Ax=b$. If $A$ is invertible, then for any $n$-vector $b$, 
$$x=A^{-1}b$$
is the only solution of the equations. This follows since $A^{-1}$ is a right inverse and a left inverse of $A$. 

> The square system of linear equations $Ax=b$, with $A$ invertible, has the unique solution $x=A^{-1}b$, for any $n$-vector $b$.

## 3.3 Invertibility Conditions
For square matrices, left-invertibility, right-invertibility and invertibility are equivalent: If a matrix is square and left-invertible, then it is also right-invertible and vice-versa.

If $A$ is an $n \times n$ matrix and left-invertible, then the $n$ columns of $A$ are linearly independent. Therefore, they form a basis, and any $n$-vector can be expressed as a linear combination of the columns of $A$. E.g., each of the $n$ unit vectors $e_i$ can be expressed as $e_i=Ab_i$. The matrix $B= \begin{bmatrix*}[r] b_1 & b_2 & \cdots & b_n \end{bmatrix*}$ satisfies
$$
AB = \begin{bmatrix*}[r]
Ab_1 & Ab_2 & \cdots & Ab_n
\end{bmatrix*} = \begin{bmatrix*}[r]
e_1 & e_2 & \cdots & e_n
\end{bmatrix*} = I.
$$
So $B$ is a right inverse of $A$.
$$
\text{left-invertibility} \Longrightarrow \text{column independence} \Longrightarrow \text{right-invertibility}
$$
Applying the result to the transpose of $A$ concludes that
$$
\text{right-invertibility} \Longrightarrow \text{row independence} \Longrightarrow \text{left-invertibility}
$$
If any of the six conditions holds, so do the other five.
In summary, for a square matrix $A$, the following are equivalent:
- $A$ is invertible.
- The columns of $A$ are linearly independent.
- The rows of $A$ are linearly independent.
- $A$ has a left inverse.
- $A$ has a right inverse.
## 3.4 Inverse of Matrix Transpose
If $A$ is invertible, its transpose $A^T$ is also invertible and its inverse $(A^{-1})^T$:
$$(A^T)^{-1}=(A^{-1})^T$$
## 3.5 Inverse of Matrix Product
If $A$ and $B$ are invertible (hence, square) and of the same size, then $AB$ is invertible, and 
$$
(AB)^{-1}=B^{-1}A^{-1}
$$
The inverse of a product is the product of the inverses, in reverse order.
## 3.6 Dual Basis
Suppose that $A$ is invertible with inverse $B=A^{-1}$. Let $a_1, \dots, a_n$ be the columns of $A$, and $b_1^T, \dots, b_n^T$ denote the rows of $B$, i.e., the columns of $B^T$:
$$
A = \begin{bmatrix*}[r]
a_1 & \cdots & a_n
\end{bmatrix*}, \quad B = \begin{bmatrix*}
b_1^T \\
\vdots \\
b_n^T
\end{bmatrix*}
$$
We know that $a_1, \dots, a_n$ form a basis. The vectors $b_1, \dots, b_n$, also form a basis. They are called the dual basis of $a_1, \dots, a_n$.

Suppose $x$ is any $n$-vector. It can be expressed as a linear combination of the basis vectors $a_1, \dots, a_n$:
$$x=\beta_1 a_1+ \cdots + \beta_na_n$$
The dual basis gives us a way to find the coefficients $b_1, \dots, \beta_n$.

We start with $AB = I$, and multiply by $x$ to get
$$
x = ABx = \begin{bmatrix*}[r]
a_1 & \cdots & a_n
\end{bmatrix*}\begin{bmatrix*}
b_1^T \\ \vdots \\ b_n^T
\end{bmatrix*}x = (b_1^Tx)a_1+\cdots+(b_n^Tx)a_n.
$$
This means that $\beta_i=b_i^Tx$. In words: The coefficients in the expansion of a vector in a basis are given by the inner products with the dual basis vectors. Using matrix notation, we can say that $\beta = B^Tx=(A^{-1})^Tx$ is the vector of coefficients of $x$ in the basis given by the columns of $A$. 

### 3.6.1 Example
Consider the basis
$$
a_1=(1,1), \quad a_2(1,-1).
$$
The dual basis consists of the rows of $\begin{bmatrix*}[r]a_1 & a_2\end{bmatrix*}^{-1}$, which are
$$
b_1^T = \begin{bmatrix*}[r]
1/2 & 1/2
\end{bmatrix*}, \quad b_2^T = \begin{bmatrix*}[r]
1/2 & -1/2
\end{bmatrix*}.
$$
To express the vector $x=(-5,1)$ as a linear combination of $a_1, a_2$, we have
$$
x=(b_1^Tx)a_1+(b_2^Tx)a_2=(-2)a_1+(-3)a_2
$$
## 3.7 Triangular Matrix
A triangular matrix with nonzero diagonal elements is invertible. 
## 3.8 Inverse via QR Factorization
The QR factorization gives a simple expression for the inverse of an invertible matrix. If $A$ is square and invertible, its columns are linearly independent, so it has a QR factorization $A=QR$. The matrix $Q$ is orthogonal and $R$ is upper triangular with positive diagonal entries. Hence, $Q$ and $R$ are invertible, and the formula for the inverse product gives
$$
A^{-1}=(QR)^{-1}=R^{-1}Q^{-1}=R^{-1}Q^T.
$$
# 4 Solving Linear Equations
## 4.1 Back Substitution
Given an $n \times n$ upper triangular matrix $R$ with nonzero diagonal entries, and an $n$-vector $b$, we can solve the set of linear equations $Rx=b$ with the following method.
We write out the equations as
$$
\begin{aligned}
R_{11}x_1+R_{12}x_2+\cdots+R_{1,n-1}x_{n-1}+R_{1n}x_n &= b_1 \\
&\;\;\vdots \\
R_{n-2,n-2}x_{n-2}+R_{n-2,n-1}x_{n-1}+R_{n-2,n}x_n &= b_{n-2} \\
R_{n-1,n-1}x_{n-1}+R_{n-1,n}x_n &= b_{n-1} \\
R_{nn}x_n&=b_n.
\end{aligned}
$$
From the last equation, we find that $x_n=b_n/R_{nn}$. now, that we know $x_n$, we can substitute it into the second to last equation, which gives us
$$
x_{n-1}=(b_{n-1}-R_{n-1,n}x_n)/R_{n-1,n-1}.
$$
### 4.1.1 Example
Let
$$
R = \begin{bmatrix*}[r]
2 & -1 & 0 \\ 0 & 3 & 1 \\ 0 & 0 & 4
\end{bmatrix*}, \quad b= \begin{bmatrix*}[r]
1 \\ 7 \\ 8
\end{bmatrix*}.
$$
Last equation $x_3$:
$$
4x_3=8 \Longrightarrow x_3 = 8/4 = 2
$$
Second last equation $x_2$ with $i=2$
$$
3x_2+1x_3=7 \Longrightarrow 3x_2+2=7 \Longrightarrow 3x_2=5 \Longrightarrow x_2=\frac53
$$
First equation $x_1$ with $i=1$:
$$
2x_1+(-1x_2)+0x_3=1 \Longrightarrow 2x_1+\left(-\frac53\right)=1 \Longrightarrow 2x_1=\frac83 \Longrightarrow x_1=\frac43
$$
So the solution is:
$$
x = \begin{bmatrix*}
4/3 \\ 5/3 \\ 2
\end{bmatrix*}
$$
## 4.2 Solving Linear Equations Using the QR Factorization
$$A^{-1}=(QR)^{-1}=R^{-1}Q^{-1}=R^{-1}Q^T$$
The formula (above) for the inverse of a matrix in terms of its QR factorization suggests a method for solving a square system of linear equations $Ax=b$ with $A$ invertible.  The solution
$$
x=A^{-1}b=R^{-1}Q^Tb
$$
can be found by first computing the matrix-vector product $y=Q^Tb$, and then solving the triangular equation $Rx=y$ by back substitution.
## 4.3 Computing The Matrix Inverse
We can now describe a method to compute the inverse $B=A^{-1}$ of an invertible $n \times n$ matrix $A$. 
We first compute the QR factorization of $A$, so $A^{-1}=R^{-1}Q^T$ using the following method

1. QR Factorization
$$
\tilde q_i = a_i - \sum_{j=1}^{i-1}(q_j^Ta_i)q_j
$$
Let $r_{ii} = \Vert \tilde q_i \Vert$, and set 
$$q_i = \frac{\tilde q_i}{r_{ii}}$$
Also for $j < i$ define $r_{ji} = q_j^Ta_i$.
[[QR Factorization Example|example]]

We can write this as $RB=Q^T$, which, written out by columns is
$$
\begin{aligned}
&Rb_i=\tilde q_i, &i=1, \dots, n,
\end{aligned}
$$
where $b_i$ is the $i$th column of $B$ and $\tilde q_i$ is the $i$th column of $Q^T$. We can solve these equations using back substitution, to get the columns of the inverse $B$.
# 5 Pseudo-Inverse
## 5.1 Pseudo-Inverse Of Square or Tall Matrix
Assuming $A$ has linearly independent columns, we know that $A^TA$ is invertible. We now observe that the matrix $(A^TA)^{-1}A^T$ is a left inverse of $A$:
$$
\left( \left(A^TA\right)^{-1}A^T \right)A=(A^TA)^{-1}(A^TA)=I
$$
This particular left-inverse of $A$ is called the pseudo-inverse of $A$, and is denoted $A^\dagger$ (or $A^+$):
$$
A^\dagger=(A^TA)^{-1}A^T.
$$
When $A$ is square, the pseudo-inverse $A^\dagger$ reduces to the ordinary inverse:
$$
A^\dagger = (A^TA)^{-1}A^T=A^{-1}A^{-T}A^T=A^{-1}I=A^{-1}
$$
## 5.2 Pseudo-Inverse Of a Square or Wide Matrix
A matrix $A$ has a right inverse if and only if its rows are linearly independent. Indeed, one right inverse is given by
$$
A^T(AA^T)^{-1}.
$$
This matrix is also referred to as the pseudo-inverse of $A$, and denoted $A^\dagger$. 
## 5.3 Pseudo-Inverse via QR Factorization
If $A$ is left-invertible, its columns are linearly independent and the QR factorization $A=QR$ exists. We have
$$
A^TA=(QR)^T(QR)=R^TQ^TQR=R^TR
$$
so
$$
A^\dagger=(A^TA)^{-1}A^T=(R^TR)^{-1}(QR)^T=R^{-1}R^{-T}R^TQ^T=R^{-1}Q^T.
$$
If $A$ is right-invertible, the QR factorization $A^T=QR$ of its transpose exists and we can compute it using the formula
$$
(A^T)^\dagger=(A^\dagger)^T.
$$
