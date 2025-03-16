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
# 2 Different Matrices
## 2.1 Zero Matrices
A zero matrix is a matrix with all elements equal to zro. The zero matrix of size $m \times n$ is sometimes written as $0_{m \times n}$ but usually a zero matrix is denoted just 0.
## 2.2 Identity Matrices
An identity matrix is always square. Its diagonal elements, i.e., those with equal row and column indices, are all equal to one, and its off-diagonal elements are zero. Identity matrices are denoted by the letter $I$. Formally, the identity matrix of size $n$ is defined by 
$$
I_{i j} = \begin{cases}
1 & i = j \\ 
0 & i \neq j
\end{cases}
$$
for $i,j=1, \dots, n$. For example,
$$ 
\begin{align}
&\left[ \; 
\begin{matrix} 
1 & 0 \\
0 & 1
\end{matrix} 
\; \right], &\left[ \; 
\begin{matrix} 
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{matrix} 
\; \right]
\end{align}
$$
## 2.3 Sparse Matrices
A matrix $A$ is said to be sparse if many of its entries are zero. Its *sparsity pattern* is the set of indices $(i,j)$ for which $A_{ij} \neq 0$. The number of nonzeros of a sparse matrix $A$ is the number of entries in its sparsity patter, and denoted $\mathbf{nnz}(A)$. If $A$ is $m \times n$ we have $\mathbf{nnz}(A) \leq mn$. Its density is $\mathbf{nnz}(A)/(mn)$, which is no more than one. Densities of sparse matrices that arise in applications are typically very small, as in $10^{-2}$ or $10^{-4}$. There is no precise definition of how small the density must be for a matrix to qualify as sparse. 

An $n \times n$ identity matrix is sparse, since it has only $n$ nonzeros, so its density is $1/n$. The zero matrix is the sparsest possible, since it has no nonzero entries.
## 2.4 Diagonal Matrices
A square $n \times n$ matrix $A$ is *diagonal* if $A_{ij}=0$ for $i \neq j$. 

The notation $\mathbf{diag}(a_1, \dots, a_n)$ is used to compactly describe the $n \times n$ diagonal matrix $A$ with diagonal entries $A_{11}=a_1, \dots, A_{nn}=a_n$. 
### 2.4.1 Example
$$ 
\begin{align}
&\left[ \; 
\begin{matrix} 
-3 &0 \\
0 &0
\end{matrix} 
\; \right], &\left[ \; 
\begin{matrix} 
0.2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 1.2
\end{matrix} 
\; \right].
\end{align}
$$
Note that while the diagonal elements can be zero, all the non-diagonal elements have to be zero for it to be a diagonal matrix.

The examples above can be noted as
$$ 
\begin{align}
&\mathbf{diag}(-3, 0) &\mathbf{diag}(0.2, -3, 1.2)
\end{align}
$$
## 2.5 Triangular Matrices
A square $n \times n$ matrix $A$ is *upper triangular* if $A_{ij}=0$ for $i > j$, and it is *lower triangular* if $A_{ij}=0$ for $i < j$. (So a diagonal matrix is one that is both lower and upper triangular). If a matrix is either lower or upper triangular, it is called *triangular*. For example, the matrices
$$ 
\begin{align}
&\left[ \; 
\begin{matrix} 
1 & -1 & 0.7 \\
0 & 1.2 & -1.1 \\
0 & 0 & 3.2
\end{matrix} 
\; \right], &\left[ \; 
\begin{matrix} 
-0.6 & 0 \\
-0.3 & 3.5
\end{matrix} 
\; \right]
\end{align}
$$
are upper and lower triangular, respectively.

A triangular $n \times n$ matrix $A$ has up to $n(n+1)/2$ nonzero entries, i.e., around half its entries are zero. Triangular matrices are generally not considered sparse matrices, since their density is around 50%. 
# 3 Transposition, Addition and Norms
## 3.1 Transposition
If $A$ is an $m \times n$ matrix, its *transpose*, denoted by $A^T$ (or sometimes $A'$ or $A^*$), is the $n \times m$ matrix given by $(A^T)_{ij}=A_{ji}$. In words, the rows and columns of $A$ are transposed in $A^T$. For example,
$$
\left[ \; 
\begin{matrix} 
0 & 4 \\
7 & 0 \\
3 & 1
\end{matrix} 
\; \right]^T
= \left[ \; 
\begin{matrix} 
0 & 7 & 3 \\
4 & 0 & 1
\end{matrix} 
\; \right].
$$
If we transpose a matrix twice, we get the original matrix $(A^T)^T=A$. The superscript $T$ in the transpose is the same one used to denote the inner product of two $n$-vectors.

Transposition converts row vectors into column vectors and vice verse. It is sometimes convenient to express a row vector as $a^T$, where $a$ is a column vector. We might refer to the $m$ rows of an $m \times n$ matrix $A$ as $\tilde{a}_i^T, \dots, \tilde{a}_m^T$, where $\tilde a_1, \dots, \tilde a_m$ are column $n$-vectors. As an example, the second row of the matrix 
$$
\left[ \; 
\begin{matrix} 
0 & 7 & 3 \\
4 & 0 & 1
\end{matrix} 
\; \right]
$$
can be written as (the row vector) $(4,0,1)^T$.
### 3.1.1 Transpose of Block Matrices
The transpose of a block matrix has the simple form
$$
\left[ \; 
\begin{matrix} 
A & B \\
C & D
\end{matrix} 
\; \right]^T
= \left[ \; 
\begin{matrix} 
A^T & C^T \\
B^T &D^T
\end{matrix} 
\; \right],
$$
where $A,B,C,D$ are matrices with compatible sizes. The transpose of a block matrix is the transposed block matrix, with each element transposed.
## 3.2 Addition
Two matrices of the same size can be added together. The result is another matrix of the same size, obtained by adding the corresponding elements of the two matrices. For example, 
$$
\left[ \; 
\begin{matrix} 
0 & 4\\ 7 & 0 \\ 3 & 1
\end{matrix} 
\; \right] + \left[ \; 
\begin{matrix} 
1 & 2 \\ 2 & 3 \\ 0 & 4
\end{matrix} 
\; \right] = \left[ \; 
\begin{matrix} 
1 & 6 \\ 9 & 3 \\ 3 & 5
\end{matrix} 
\; \right].
$$
Matrix subtraction is similar. For example,
$$
\left[ \; 
\begin{matrix} 
1 & 6 \\ 9 & 3
\end{matrix} 
\; \right]- I = \left[ \; 
\begin{matrix} 
0 &6 \\ 9&2
\end{matrix} 
\; \right]
$$
## 3.3 Scalar-Matrix Multiplication
Scalar multiplication of matrices is defined in a similar way as for vectors, and is done by multiplying every element of the matrix by the scalar. For example
$$
(-2)
\left[ \; 
\begin{array}{r}
1 & 6 \\ 9 & 3 \\ 6 & 0
\end{array} 
\; \right]
= 
\left[ \; 
\begin{array}{r}
-2 & -12 \\ -18 & -6 \\ -12 & 0
\end{array} 
\; \right]
$$
## 3.4 Matrix Norms
The norm of an $m \times n$ matrix $A$, denoted $\Vert A \Vert$, is the squareroot of the sum of the squares of its entries,
$$
\Vert A \Vert = \sqrt{\sum_{i=1}^m \sum_{j=1}^n A^2_{ij}}
$$
The norm of an $m \times n$ matrix is the norm of an $mn$-vector formed from the entries of the matrix in any order. The matrix norm is a quantitative measure of the magnitude of a matrix. The RMS of the matrix entries can be found with $\Vert A \Vert / \sqrt{mn}$. This tells us the typical size of the entries, independent of the matrix dimensions.

For any two $m \times n$ matrices $A$ and $B$, we have the triangle inequality,
$$
\Vert A + B \Vert \leq \Vert A \Vert + \Vert B \Vert.
$$
The matrix norm allows us to define the distance between two matrices as $\Vert A - B \Vert$. 

$$
\Vert A \Vert ^2 = \Vert a_1 \Vert^2 + \cdots + \Vert a_n \Vert^2,
$$
where $a_1, \dots, a_n$ are the columns of A, i.e., the squared norm of a matrix is the sum of the squared norms of its columns.
## Matrix-Vector multiplication
If $A$ is an $m \times n$ matrix and $x$ is an $n$-vector, then the *matrix-vector product* $y=Ax$ is the $m$-vector $y$ with elements
$$
y_i=\sum_{k=1}^n A_{ik}x_k=A_{i1}x_1+\cdots A_{in}x_n
,\quad i=1, \dots, m.
$$
For example,
$$
\left[ \; 
\begin{matrix} 
0 & 2 & -1 \\ -2 & 1 & 1
\end{matrix} 
\; \right]
\left[ \; 
\begin{matrix} 
2 \\ 1 \\ -1
\end{matrix} 
\; \right]
= \left[ \; 
\begin{matrix} 
(0)(2)+(2)(1)+(-1)(-1) \\
(-2)(2)+(1)(1)+(1)(-1)
\end{matrix} 
\; \right]= \left[ \; 
\begin{array}{r}
3 \\ -4
\end{array} 
\; \right].
$$
# 4 Definitions
## 4.1 Square
A *square* matrix has an equal amount of rows and columns. A square matrix of size $n \times n$ is said to be of *order* $n$. 
## 4.2 Tall
A *tall* matrix has more rows than columns (size $m \times n$ with $m > n$).
## 4.3 Wide
A *wide* matrix has more columns than rows (size $m \times n$ with $n > m$).