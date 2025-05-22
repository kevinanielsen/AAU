# Literature
Chapter 11 + Slides
# Left and Right Inverses
Recall that for a number $a$, its (multiplicative) inverse is the number $x$ for which $xa=1$, which we usually denote as $x=1/a$ or $x=a^{-1}$. 
## Left Inverse
A matrix $X$ that satisfies
$$XA=I$$
is called a left inverse of $A$. The matrix $A$ is said to be left-invertible if a left inverse exists. Note, that if $A$ has size $m \times n$, a left inverse $X$ will have size $n \times m$, the same dimensions as $A^T$.
### Example
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

## Left-Invertibility and Column Independence
If $A$ has a left inverse $C$ then the columns of $A$ are linearly independent.
To see this, suppose that $Ax=0$
$$
0=C(Ax)=(CA)x=Ix=x
$$
## Dimensions of Left Inverses
Suppose the $m \times n$ matrix $A$ is wide. By the [[K02 - Linear Independence#3.1 Independence-Dimension Inequality|independence-dimension inequality]], its columns are linearly dependent, and therefore it is not left-invertible. **Only square or tall matrices can be left-invertible.**
## Solving Linear Equations With a Left Inverse
Suppose that $Ax=b$, where $A$ is an $m \times n$ matrix and $x$ is an $n$-vector. If $C$ is a left inverse of $A$, we have
$$
Cb=C(Ax)=(CA)x=Ix=x,
$$
which means that $x=Cb$ is a solution of the set of linear equations. The columns of $A$ are linearly independent (since it has a left inverse), so there is only one solution of the linear equations $Ax=b$, i.e., $x=Cb$ is the solution of $Ax=b$. 

If there is no $x$ that satisfies the linear equations $Ax=b$ and $C$ is a left inverse of $A$. Then $x=Cb$ does not satisfy $Ax=b$, since no vector satisfies this equation by assumption. This gives a way to find a solution to linear equations when there is one, provided we have a left inverse of $A$. We simply test whether $A(Cb)=b$. If this holds, then we have found a solution of the linear equations; if it doesn't, then we can conclude there is no solution of $Ax=b$.
## Right Inverse
A matrix $X$ that satisfies
$$AX=I$$
Is called a right inverse of $A$. The matrix $A$ is right-invertible if a right inverse exists. Any right inverse has the same dimensions as $A^T$. 
## Left and Right Inverse of Matrix Transpose
If $A$ has a right inverse $B$, then $B^T$ is a left inverse of $A^T$, since $B^TA^T=(AB)^T=I$. 
- A matrix is right-invertible if and only if its rows are linearly independent.
- A tall matrix cannot have a right inverse. Only square or wide matrices can be right-invertible.
## Solving Linear Equations With a Right Inverse
Consider the set of $m$ linear equations in $n$ variables $Ax=b$. Suppose $A$ is right-invertible, with right inverse $B$. This implies that $A$ is square or wide, so lienar equations $Ax=b$ are square or under-determined.

Then, for any $m$-vector $b$, the $n$-vector $x=Bb$ satisfies the equation $Ax=b$. 

In summary, a right inverse can be used to find a solution of a square or under-determined set of linear equations, for any vector $b$.
# Inverse
If a matrix is left- and right-invertible, then the left and right inverses are unique and equal. To see this, suppose that $AX=I$ and $YA=I$, i.e., $X$ is any right inverse and $Y$ is any left inverse of $A$. Then we have
$$
X=(YA)X=Y(AX)=Y,
$$
i.e., any left inverse of $A$ is equal to any right inverse of $A$. 

When a matrix is both right- and left-invertible, it is denoted as $A^{-1}$ and called invertible or nonsingular. A square matrix that is not invertible is called singular.

## Dimensions of Invertible Matrices
Invertible matrices must be square.
## Solving Linear Equations With the Inverse
Consider the square system of $n$ linear equations with $n$ variables, $Ax=b$. If $A$ is invertible, then for any $n$-vector $b$, 
$$x=A^{-1}b$$
is the only solution of the equations. This follows since $A^{-1}$ is a right inverse and a left inverse of $A$. 

> The square system of linear equations $Ax=b$, with $A$ invertible, has the unique solution $x=A^{-1}b$, for any $n$-vector $b$.

## Invertibility Conditions
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
## Inverse of Matrix Transpose
If $A$ is invertible, its transpose $A^T$ is also invertible and its inverse $(A^{-1})^T$:
$$(A^T)^{-1}=(A^{-1})^T$$
