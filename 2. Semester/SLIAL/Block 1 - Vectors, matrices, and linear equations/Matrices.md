# 1 Basics
A *matrix* is a rectangular array of numbers written between rectangular brackets, as in
$$
\left[\begin{array}{cccc}0 & 1 & -2.3 & 0.1 \\ 1.3 & 4 & -0.1 & 0 \\ 4.1 & -1 & 0 & 1.7\end{array}\right].
$$
It is also common to use large parentheses instead of rectangular brackets, as in
$$
\left(\begin{array}{cccc}0 & 1 & -2.3 & 0.1 \\ 1.3 & 4 & -0.1 & 0 \\ 4.1 & -1 & 0 & 1.7\end{array}\right).
$$
Its size is given by (row dimension) $\times$ (column dimension) e.g. the matrix above is $3 \times 4$. 

$B_{ij}$ is the $i,j$ element of matrix $B$ where $i$ is the row index, $j$ is the column index; indexes start at 1.

Two matrices are equal if they have the same size and corresponding entries are equal.

The set of real $m \times n$ matries is denoted by $\mathbf{R}^{m \times n}$.

An $n$-vector can be interpreted as an $n \times 1$ matrix. A matrix with only one row, i.e., with size $1 \times n$, is called a row vector. A $1 \times 1$ matrix is considered to be the same as a scalar.
## 1.1 Columns and rows of a matrix
An $m \times n$ matrix $A$ has $n$ columns, given by (the $m$-vectors)
$$
a_j = \left[ \; 
\begin{matrix} 
A_{1j} \\
\vdots \\
A_{mj}
\end{matrix} 
\; \right]
$$
for $j=1, \dots, n$. The same matrix has $m$ rows, given by the $n$-row-vectors
$$
b_i = \left[ \; 
\begin{matrix} 
A_{i1} \quad \cdots \quad A_{in}
\end{matrix} 
\; \right],
$$
for $i=1, \dots, m$.
### 1.1.1 Example
The $2 \times 3$ matrix
$$
\left[ \; 
\begin{matrix} 
1 \quad 2 \quad 3 \\
4 \quad 5 \quad 6
\end{matrix} 
\; \right]
$$
has the first row
$$
\left[ \; 
\begin{matrix} 
1 \quad 2 \quad 3
\end{matrix} 
\; \right]
$$
Which is a 3-row-vector or a $1 \times 3$ matrix), and second column
$$
\left[ \; 
\begin{matrix} 
2 \\ 5
\end{matrix} 
\; \right]
$$
which is a 2-vector or $2\times 1$ matrix.
## 1.2 Block matrices
Matrices whose entries are matrices themselves are called block matrices and are denoted by
$$
A = \left[ \; 
\begin{matrix} 
B \quad C \\
D \quad E
\end{matrix} 
\; \right],
$$
where $B, C, D, E$ are matrices and are usually referred to as *blocks* or *submatrices* of $A$. They can be referred to by their block row and column indices; for example, $C$ is the $1,2$ block of $A$. 

Matrices in the same (block) row must have the same number of rows (i.e., the same height), matrices in the same (block) column must have the same number of columns (i.e., the same width). In the example above, $B, C$ must have the same number of rows, and $C,E$ must have the same number of columns. Matrix blocks placed next to each other in the same row are said to be *concatenated*, and matrix blocks that are placed above each other are called *stacked*.
### 1.2.1 Example
Consider
$$
\begin{aligned}
&B = \left[ \; 
\begin{matrix} 
0 \quad 2 \quad 3
\end{matrix} 
\; \right],
&&C = \left[ \; 
\begin{matrix} 
-1
\end{matrix} 
\; \right],
&D = \left[ \; 
\begin{matrix} 
2 \quad 2 \quad 1 \\
1 \quad 3 \quad 5
\end{matrix} 
\; \right],
&&E = \left[ \; 
\begin{matrix} 
4 \\
4
\end{matrix} 
\; \right].
\end{aligned}
$$
Then the block matrix $A$ above is given by
$$
A = \left[ \; 
\begin{matrix} 
0 &2 &3 &-1 \\
2 &2 &1 &4 \\
1 &3 &5 &4
\end{matrix} 
\; \right].
$$
## 1.3 Submatrices
If $A$ is an $m \times n$ matrix, and $p,q,r,s$ are integers with $1 \leq p \leq q \leq m$ and $1 \leq r \leq s \leq n$, then $A_{p:q,r:s}$ denotes the submatrix
$$
A_{p:q,r:s} = \left[ \; 
\begin{matrix} 
A_pr & A_{p,r+1} & \cdots & A_{ps} \\
A_{p+1,r} & A_{p+1,r+1} & \cdots & A_{p+1,s} \\
\vdots & \vdots && \vdots \\
A_{qr} & A_{q,r+1} & \cdots & A_{qs}
\end{matrix} 
\; \right]
$$
This submatrix has size $(q-p+1) \times (s-r+1)$.

For the specific matrix $A$ from the [[Matrices#1.2 Block matrices#1.2.1 Example|example above]], we have
$$
A_{2:3,3:4} = \left[ \; 
\begin{matrix} 
1 & 4 \\
5 & 4
\end{matrix} 
\; \right]
$$
# 2 Zero and Identity Matrices

# 3 Definitions
## 3.1 Square
A *square* matrix has an equal amount of rows and columns. A square matrix of size $n \times n$ is said to be of *order* $n$. 
## 3.2 Tall
A *tall* matrix has more rows than columns (size $m \times n$ with $m > n$).
## 3.3 Wide
A *wide* matrix has more columns than rows (size $m \times n$ with $n > m$).