**Literature:** Section 5.1 of [Lay]="Linear Algebra and Its Applications" by Lay, Lay, McDonald (attached) + slides. Lay gives the definitions and explains the way of computing eigenvectors given the knowledge of an eigenvalue. QR (and other) algorithms are used in practice to compute eigenvalues.

# 1 Eigenvector
An eigenvector of an $n \times n$ matrix $A$ is a nonzero vector $x$ such that $Ax=\lambda x$ for some scalar $\lambda$. A scalar $\lambda$ is called an eigenvalue of $A$ if there is a nontrivial solution $x$ of $Ax=\lambda x$; such an $x$ is called an eigenvector corresponding to $\lambda$.

If there are solutions to $(A-\lambda I)x=0$, the set of solutions are called the eigenspace.

Note: Eigenvalue can be zero, but the eigenvector cannot be a zero vector.

## 1.1 Examples
**Example 1**
Let $A = \begin{bmatrix*}[r] 1 & 6 \\ 5 & 2 \end{bmatrix*}, u = \begin{bmatrix*}[r] 6 \\ -5 \end{bmatrix*}$, and $v  = \begin{bmatrix*}[r] 3 \\ -2 \end{bmatrix*}$. Are $u$ and $v$ eigenvectors of $A$?

$$
\begin{aligned}
Au = \begin{bmatrix*}[r]
1 & 6 \\ 5 & 2
\end{bmatrix*}\begin{bmatrix*}[r]
6 \\ -5
\end{bmatrix*} &= \begin{bmatrix*}[r]
-24 \\ 20
\end{bmatrix*} = -4 \begin{bmatrix*}[r]
6 \\ -5
\end{bmatrix*}=-4u \\
Av = \begin{bmatrix*}[r]
1 & 6 \\ 5 & 2
\end{bmatrix*} \begin{bmatrix*}[r]
3 \\ -2
\end{bmatrix*} &= \begin{bmatrix*}[r]
-9 \\ 11
\end{bmatrix*} \ne \lambda \begin{bmatrix*}[r]
3 \ -2
\end{bmatrix*}
\end{aligned}
$$
Thus $u$ is an eigenvector corresponding to an eigenvalue $(-4)$, but $v$ is not an eigenvector of $A$. 

**Example 2**
$v= \begin{bmatrix*}[r] 2 \\ -1 \end{bmatrix*}$ is an eigenvector, $A = \begin{bmatrix*}[r] 7 & 4 \\ -3 & -1 \end{bmatrix*}$. What is the corresponding eigenvalue?

$$Av = \begin{bmatrix*}[r] 7 & 4 \\ -3 & -1 \end{bmatrix*} \begin{bmatrix*}[r] 2 \\ -1 \end{bmatrix*} = \begin{bmatrix*}[r] 10 \\-5 \end{bmatrix*}=5 \cdot \begin{bmatrix*}[r] 2 \\ -1 \end{bmatrix*}$$
**Example 3**
Is $v = \begin{bmatrix*}[r] 2 \\-1 \end{bmatrix*}$ an eigenvector for $B = \begin{bmatrix*}[r] 2 & 3 \\ 0 & -1 \end{bmatrix*}$?
$$
Bv = \begin{bmatrix*}[r]
2 & 3 \\ 0 & -1
\end{bmatrix*} \begin{bmatrix*}[r]
2 \\ -1
\end{bmatrix*} = \begin{bmatrix*}[r]
1 \\ 1
\end{bmatrix*} \Longrightarrow \text{No.}
$$
# 2 Computing Eigenvectors
Assume that $\lambda$ is an eigenvalue. How do we find a corresponding eigenvector?

From the definition, the eigenvector $v$ should satisfy
$$Av = \lambda v, \quad v \ne 0$$
Thus, we need to find a non-zero solution to the system
$$
\begin{aligned}
Av- \lambda v = 0, &\quad v \ne 0 \\
(A-\lambda I)v=0, &\quad v \ne 0
\end{aligned}
$$
## 2.1 Examples
**Example 1**
$\lambda = 10$ is an eigenvalue for $A = \begin{bmatrix*}[r] 4 & -2 \\ -3 & 9 \end{bmatrix*}$.
What is the corresponding eigenvector?
$$
\begin{aligned}
A - \lambda I = \begin{bmatrix*}
4-10 & -2 \\
-3 & 9-10 
\end{bmatrix*} = \begin{bmatrix*}[r]
-6 & -2 \\
-3 & -1
\end{bmatrix*}
\end{aligned}
$$
Since the rows are linearly dependent (the first row is the second scaled by 2), there will be a nonzero solution to the system $(A - \lambda I)v = 0$. To find the solution, we will do gaussian elimination:
$$
\begin{bmatrix*}[r]
-6 & -2 & | & 0 \\
-3 & -1 & | & 0
\end{bmatrix*} \sim \begin{bmatrix*}[r]
-6 & -2 & | & 0 \\
0 & 0 & | & 0
\end{bmatrix*}
$$
As we can see, the last column has no pivot, i.e., it is a consistent system and has at least a solution. Furthermore, the second column has no pivot (it is a free variable), i.e., there are many solutions.
$$
\begin{aligned}
-6x_1-2x_2&=0 \\
x_1 &= -\frac13x_2
\end{aligned}
$$
Since it is free, we can set the value of $x_2$ to pretty much anything. If we set it to $x_2=3$, that gives $x_1=-1$, and we get the eigenvector $v = \begin{bmatrix*}[r] x_1 \\ x_2\end{bmatrix*} = \begin{bmatrix*}[r] -1 \\ 3 \end{bmatrix*}$.

To see if this is correct, we can compute $Av$ and check if it equals $10v$:
$$
\begin{bmatrix*}[r]
4 & -2 \\ -3 & 9
\end{bmatrix*} \begin{bmatrix*}[r]
-1 \\ 3
\end{bmatrix*} = \begin{bmatrix*}[r]
-4+(-6) \\ 3 +27
\end{bmatrix*} = \begin{bmatrix*}[r]
-10 \\ 30
\end{bmatrix*} = 10 \begin{bmatrix*}[r]
-1 \\ 3
\end{bmatrix*}
$$
# 3 Computing Eigenvalues
What happens, if $A- \lambda I$ is invertible? Then $v = (A- \lambda I)^{-1}0=0$ 

Therefore, for $\lambda$ to be an eigenvalue we need to require that
$A-\lambda$ is not invertible.

## 3.1 Triangular (and Diagonal) Matrices
## 3.2 Exampels
**Example 1**
Eigenvalues for $A=\begin{bmatrix*}[r] 4 & \sqrt2 & \pi \\ 0 & 1 & 99 \\ 0 & 0 & -2 \end{bmatrix*}$ are on the diagonal
$$
A-(-2)I= \begin{bmatrix*}[r]
6 & \sqrt2 & \pi \\
0 & 3 & 99 \\
0 & 0 & 0
\end{bmatrix*}
$$
Since one of the diagonals is zero, the matrix is not invertible. This confirms that the diagonal values of a triangular matrix are eigenvalues.

## 3.3 Eigenvalues and Row Operations
Note: We *cannot* use row (or column) operations to determine eigenvalues. I.e., if $A$ is row equivalent to $R$, the eigenvalues of $R$ (generally speaking) give no information about the eigenvalues of $A$

(We can use row operations to compute an eigenvector by solving the system $(A - \lambda I)v=0$ provided that eigenvalue is known as seen earlier).

- For matrices larger than $5 \times 5$ one has to use iterative numerical algorithms
- If we know an eigenvector, the corresponding eigenvalue can be determined from the equality
$$Av=\lambda v$$