# 1 Literature
Chapter 12 + slides
# 2 Least Squares Problem
Suppose that the $m \times n$ matrix $A$ is tall, so the system of linear equations $Ax=b$, where $b$ is an $m$-vector, is over-determined, i.e., there are more equations $(m)$ than variables to choose $(n)$. These equations have a solution only if $b$ is a linear combination of the columns of $A$. 

For most choices of $b$, there is no $x$ that satisfies $Ax=b$, so we seek an $x$ where the residual $r=Ax-b$, is as small as possible. The least squares problem: Choose $x$ to minimize $\Vert Ax-b \Vert^2$, it is denoted as $$\text{minimize}\quad \Vert Ax-b \Vert^2$$
The *variable* is $x$ and the matrix $A$ and the vector $b$ are called the *data*.

$\hat x$ is a solution of a least squares problem if 
$$
\Vert A \hat x - b \Vert^2 \leq \Vert Ax-b \Vert ^2
$$
for any $n$-vector $x$. This is also called regression in the data fitting context.
## 2.1 Column interpretation
Suppose $a_1, \dots, a_n$ are columns of $A$, then
$$
\Vert Ax-b \Vert^2 = \Vert (x_1a_1+ \cdots + x_na_n)-b \Vert^2
$$
If $\hat x$ is a solution of least squares problem, the $m$-vector
$$A\hat x = \hat x_1a_1 + \cdots + \hat x_na_n$$
is closest to $b$ among all linear combinations of columns of $A$.
## 2.2 Row Interpretation
Suppose $\tilde a_1^T, \dots, \tilde a_m^T$ are rows of $A$, then residual components are $r_i=\tilde a_i^Tx-b_i$, and the least squares objective is
$$
\Vert Ax-b \Vert ^2=(\tilde a_1^Tx-b_1)^2+\cdots+(\tilde a_m^Tx-b_m)^2
$$
the sum of squares of the residuals.

Solving $Ax=b$ is making all residuals zero, but least squares attempts to make them all small.
## 2.3 Example
$$
\begin{aligned}
&A = \begin{bmatrix*}[r]
2 & 0 \\ -1 & 1 \\ 0 & 2
\end{bmatrix*}, &&b = \begin{bmatrix*}[r]
1 \\ 0 \\ -1
\end{bmatrix*}
\end{aligned}
$$
- $Ax=b$ has no solution.
- Least squares problem is to choose $x$ to minimize
$$
\Vert Ax-b \Vert^2=(2x_1-1)^2+(-x_1+x_2)^2+(2x_2+1)^2
$$
# 3 Solutions
To find the approximate solution of the least squares problem, we first have to compute the QR factorization of $A$:
$$A=QR$$
Then, compute $Q^Tb$.
Lastly, do back substitution to solve the triangular equation $R\hat x=Q^Tb$. 