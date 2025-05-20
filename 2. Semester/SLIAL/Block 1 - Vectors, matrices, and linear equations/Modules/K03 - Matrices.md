# 1 Literature
Chapters 6,7 + Slides
# 2 Matrices
A matrix is a rectangular array of numbers written between rectangular brackets or large parentheses
$$ 
\begin{align}
&\begin{bmatrix*}[r]
0 & 1 & -2.3 & 0.1 \\
1.3 & 4 & -0.1 & 0 \\
4.1 & -1 & 0 & 1.7
\end{bmatrix*},
&\begin{pmatrix*}[r]
0 & 1 & -2.3 & 0.1 \\
1.3 & 4 & -0.1 & 0 \\
4.1 & -1 & 0 & 1.7
\end{pmatrix*}.
\end{align}
$$
The matrix above has 3 rows and 4 columns, so its size is $3 \times 4$. A matrix of size $m\times n$ is called an $m \times n$ matrix.

The $i,j$ element is the value in the $i$th row and $j$th column, denoted by double subscripts: the $i,j$ element of a matrix $A$ is denoted $A_{ij}$ (or $A_{i,j}$, when $i$ or $j$ is more than one digit or character). The indexes start at 1.
If the matrix above is $B$, then we have $B_{13}=-2.3, B_{32}=-1$. 

Two matrices are equal if they have the same size, and the corresponding entries are all equal.

The set of real $m\times n$ matrices is denoted $\mathbf{R}^{m\times n}$. 
## 2.1 Square, Tall, and Wide Matrices
A square matrix has an equal number of rows and columns. A square matrix of size $n\times n$ is said to be of order $n$. A tall matrix has more rows than columns. A wide matrix has more columns than rows.
## 2.2 Column and Row Vectors
An $n$-vector can be interpreted as an $n\times 1$ matrix. We do not distinguish between vectors and matrices with one column. A matrix with only one row is called a row vector (size $1 \times n$). To give its size, we can refer to it as an $n$-row-vector. A $1\times1$ matrix is considered to be the same as a scalar.
## 2.3 Columns and Rows of a Matrix
An $m\times n$ matrix $A$ has $n$ columns, given by the $m$-vectors
$$a_j=
\begin{bmatrix*}
A_{1j} \\ \vdots \\ A_{mj}
\end{bmatrix*}
$$
for $j=1,\dots,n$. The same matrix has $m$ rows, given by the $n$-row-vectors
$$
b_i = \begin{bmatrix*}
A_{i1} & \cdots & A_{in}
\end{bmatrix*}
$$
for $i=1,\dots,m$.
## 2.4 Block Matrices and Submatrices
$$
A= \begin{bmatrix*}[r]
B & C \\ D & E
\end{bmatrix*}
$$
$A$ is a matrix and so are its entries, $B,C,D,E$. Such matrices are called block matrices, where the entries are called blocks or submatrices of $A$. The submatrices can be referred to by their block row and column indices; $C$ is the $1,2$ block of $A$. 

Block matrices must have the right dimensions to fit together. Matrices in the same row must have the same number of rows (i.e., the same 'height'). Likewise, matrices in the same column must have the same number of columns (i.e., the same 'width').

In the example above, $B$ and $C$ must have the same number of rows, and $C$ and $E$ must have the same number of columns. Matrix blocks placed next to each other in the same row are said to be concatenated; matrix blocks placed above each other are called stacked.
$$ 
\begin{align}
&B = \begin{bmatrix*}[r]
0 & 2 & 3
\end{bmatrix*}, &C = \begin{bmatrix*}[r]
-1
\end{bmatrix*}, &&D = \begin{bmatrix*}[r]
2 & 2 & 1 \\ 1 & 3 & 5
\end{bmatrix*}, &&E = \begin{bmatrix*}[r]
4 \\ 4
\end{bmatrix*}.
\end{align}
$$
Then the block matrix $A$ above is given by
$$
A = \begin{bmatrix*}
0 & 2 & 3 & -1 \\
2 & 2 & 1 & 4 \\
1 & 3 & 5 & 4
\end{bmatrix*}.
$$
We can divide a large matrix (or vector) into blocks, using colon notation to denote submatrices. If $A$ is an $m \times n$ matrix, and $p,q,r,s$ are integers with $1 \leq p \leq q \leq m$ and $1 \leq r \leq s \leq n$, then $A_{p:q,r:s}$ denotes the submatrix
$$
A_{p:q,r:s}= \begin{bmatrix*}
A_{pr} & A_{p,r+1} & \cdots & A_{ps} \\
A_{p+1,r} & A_{p+1,r+1} & \cdots & A_{p+1,s} \\
\vdots & \vdots && \vdots \\
A_{qr} & A_{q,r+1} & \cdots & A_{qs} \\
\end{bmatrix*}.
$$
This submatrix has size $(q-p+1)\times(s-r+1)$.

For the matrix $A$ from earlier, we have
$$
A_{2:3,3:4}= \begin{bmatrix*}[r]
1 & 4 \\
5 & 4
\end{bmatrix*}
$$
## 2.5 Column and Row Representation of a Matrix
Using block matrix notation we can write an $m\times n$ matrix $A$ as a block matrix with one block row and $n$ block columns,
$$
A = \begin{bmatrix*}[r]
a_1 & a_2 & \cdots & a_n
\end{bmatrix*},
$$
where $a_j$, which is an $m$-vectors, is the $j$th column of $A$. Thus, an $m \times n$ matrix can be viewed as its $n$ columns concatenated.

Similarly, an $m \times n$ matrix can be written as a block matrix with one block column and $m$ block rows:
$$
A = \begin{bmatrix*}
b_1 \\ b_2 \\ \vdots \\ b_m
\end{bmatrix*}
$$
where $b_i$, which is a row $n$-vector, is the $i$th row of $A$.
## 2.6 Matrix Representation of a Collection of Vectors
If $x_1,\dots,x_N$ are $n$-vectors that give the $n$ feature values for each of $N$ objects, we can collect them all into $n\times N$ matrix
$$X = \begin{bmatrix*}[r]
x_1 & x_2 & \cdots & x_N
\end{bmatrix*},$$
often called a data matrix or feature matrix.
## 2.7 Matrix Representation of a Relation or Graph
Suppose we have $n$ objects labeled $1,\dots,n$. A relation $\mathcal{R}$ on the set of objects $\{1,\dots,n\}$ is a subset of ordered pairs of objects. $\mathcal{R}$ could represent a preference relation among $n$ possible products or choices, with $(i,j) \in \mathcal{R}$ meaning that choice $i$ is preferred to choice $j$.

A relation can also be viewed as a directed graph, with nodes (or vertices) labeled $1,\dots,n$ and a directed edge from $j$ to $i$ for each $(i,j) \in \mathcal{R}$. 
![[relation_graph.png]]

The image above can be written as $$\mathcal{R} = \{(1,2), (1,3), (2,1),(2,4),(3,4),(4,1)\}.$$
A relation $\mathcal{R}$ on $\{1,\dots,n\}$ is represented by the $n \times n$ matrix $A$ with
$$
A_{ij}=\begin{cases}
\; 1 & (i,j) \in \mathcal{R} \\
\; 0 & (i,j) \notin \mathcal{R}
\end{cases}
$$
This matrix is called the adjacency matrix associated with the graph with $A_{ij}=1$ meaning there is an edge from $i$ to $j$.
$$
A= \begin{bmatrix*}[r]
0 & 1 & 1 & 0 \\
1 & 0 & 0 & 1 \\
0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0
\end{bmatrix*}.
$$
# 3 Zero and Identity Matrices
## 3.1 Zero Matrix
A matrix with all elements equal to zero. With size $m \times n$, it is sometimes written as $0_{m \times n}$, but often it is just denoted as $0$, and the size is determined from the context.
## 3.2 Identity Matrix
The identity matrix is always square. Its diagonal elements are all equal to one, and its off-diagonal elements are zero. They are denoted by the letter $I$, and the size is usually determined from the context. The identity matrix of size $n$ is formally defined by
$$
I_{ij}=\begin{cases}
\; 1 & i=j \\
\; 0 & i \neq j,
\end{cases}
$$
for $i,j=1, \dots, n$. For example,
$$ 
\begin{align}
&\begin{bmatrix*}[r]
1 & 0 \\ 0 & 1
\end{bmatrix*}, &\begin{bmatrix*}[r]
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix*}
\end{align}
$$
are the $2 \times 2$ and $4 \times 4$ identity matrices.

Using block matrix notation, we can write
$$I = \begin{bmatrix*}[r]
e_1 & e_2 & \cdots & e_n
\end{bmatrix*},$$
where $e_k$ is the $k$th unit vector of size $n$.

If 
$$A = \begin{bmatrix*}[r]
1 & 2 & 3 \\ 4 & 5 & 6
\end{bmatrix*},$$
then
$$
\begin{bmatrix*}[r]
I & A \\ 0 & I
\end{bmatrix*} = \begin{bmatrix*}[r]
1 & 0 & 1 & 2 & 3 \\
0 & 1 & 4 & 5 & 6 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1
\end{bmatrix*}.
$$
## 3.3 Sparse Matrices
A matrix $A$ is said to be sparse if many of its entries are zero. Its sparsity pattern is the set of indices $(i,j)$ for which $A_{ij} \neq 0$. The number of nonzeros of a sparse matrix $A$ is the number of entries in its sparsity pattern, and denoted $\mathbf{nnz}(A)$. Its density is $\mathbf{nnz}(A)/(mn)$, which is no more than one.

Many common matrices are sparse. An  $n \times n$ identity matrix is sparse, since it has only $n$ nonzeros, so its density is $1/n$. 
## 3.4 Diagonal Matrices
A square $n\times n$ matrix $A$ is diagonal if $A_{ij}=0$ for $i \neq j$. A diagonal matrix is one for which all off-diagonal entries are zero
$$ 
\begin{align}
&\begin{bmatrix*}[r]
-3 & 0 \\ 0 & 0
\end{bmatrix*}, & \begin{bmatrix*}[r]
0.2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 1.2
\end{bmatrix*}.
\end{align}
$$
The notation $\mathbf{diag}(a_1, \dots, a_n)$ is used to compactly describe the $n \times n$ diagonal matrix $A$ with diagonal entries $A_{11}=a_1, \dots, A_{nn}=a_n$. The matrices above would be expressed as
$$ 
\begin{align}
& \mathbf{diag}(-3,0), &\mathbf{diag}(0.2,-3,1.2).
\end{align}
$$
$\mathbf{diag}$ can also take one $n$-vector argument, as in $I=\mathbf{diag}(\mathbf{1})$. 
## 3.5 Triangular Matrices
A square $n \times n$ matrix $A$ is upper triangular if $A_{ij}=0$ for $i > j$, and it is lower triangular if $A_{ij}=0$ for $i<j$. (So a diagonal matrix is both lower and upper triangular). If a matrix is either lower or upper triangular, it is called triangular. For example, the matrices
$$ 
\begin{align}
&\begin{bmatrix*}[r]
1 & -1 & 0.7 \\ 0 & 1.2 & -1.1 \\ 0 & 0 & 3.2
\end{bmatrix*}, &\begin{bmatrix*}[r]
-0.6 & 0 \\ -0.3 & 3.5
\end{bmatrix*},
\end{align}
$$
are upper and lower triangular, respectively.

A triangular $n\times n$ matrix $A$ has up to $n(n+1)/2$ nonzero entries. Triangular matrices are generally not considered sparse, since their density is around $50\%$.
# 4 Transpose, Addition, and Norm
# 5 Matrix Transpose
If $A$ is an $m\times n$ matrix, its transpose, denoted $A^T$ (or sometimes $A'$ or $A^*$), is the $n \times m$ matrix given by $(A^T)_{ij}=A_{ij}$. In words, the rows and columns of $A$ are transposed in $A^T$. For example,
$$
\begin{bmatrix*}[r]
0 & 4 \\ 7 & 0 \\ 3 & 1
\end{bmatrix*}^T = \begin{bmatrix*}[r]
0 & 7 & 3 \\ 4 & 0 & 1
\end{bmatrix*}.
$$
If we transpose a matrix twice, we get back the original matrix: $(A^T)^T = A$. 
### 5.1.1 Row and Column Vectors
Transposition converts row vectors into column vectors and vice versa. Sometimes, a row vector can be expressed as $a^T$, where $a$ is a column vector. For example, we might refer to the $m$ rows of an $m \times n$ matrix $A$ as $\tilde a_i^T, \dots, \tilde a_m^T$, where $\tilde a_1, \dots, \tilde a_m$ are (column) $n$-vectors. As an example, the second row of the matrix
$$\begin{bmatrix*}[r]
0 & 7 & 3 \\ 4 & 0 & 1
\end{bmatrix*}$$
can be written as (the row vector) $(4,0,1)^T$.

If the rows of matrix $A$ are linearly independent, that means the columns of $A^T$ are linearly independent.
### 5.1.2 Transpose of Block Matrix
The transpose of a block matrix has the simple form 
$$
\begin{bmatrix*}[r]
A & B \\ C & D
\end{bmatrix*}^T
= \begin{bmatrix*}[r]
A^T & C^T \\
B^T & D^T
\end{bmatrix*},
$$
## 5.2 Matrix Addition
Two matrices of the same size can be added together like so
$$
\begin{bmatrix*}[r]
0 & 4 \\ 7 & 0 \\ 3 & 1
\end{bmatrix*} + \begin{bmatrix*}[r]
1 & 2 \\ 2 & 3 \\ 0 & 4
\end{bmatrix*} = \begin{bmatrix*}[r]
1 & 6 \\ 9 & 3 \\ 3 & 5
\end{bmatrix*}.
$$
Matrix subtraction is similar
$$
\begin{bmatrix*}[r]
1 & 6 \\ 9 & 3
\end{bmatrix*} - I = \begin{bmatrix*}[r]
0 & 6 \\ 9 & 2
\end{bmatrix*}.
$$
### 5.2.1 Properties of Matrix Addition
*Assuming that $A, B, C$ are of the same size*
- Commutativity: $A+B=B+A$.
- Associativity: $(A+B) + C = A + (B+C)$.
- Addition with zero matrix: $A+0 = 0+ A = A$.
- Transpose of sum: $(A+B)^T=A^T + B^T$.
## 5.3 Scalar-Matrix Multiplication
Scalar multiplication of matrices is done by multiplying every element of the matrix by the scalar.
$$
(-2)\begin{bmatrix*}[r]
1 & 6 \\ 9 & 3 \\ 6 & 0
\end{bmatrix*} = \begin{bmatrix*}[r]
-2 & -12 \\ -18 & -6 \\ - 12 & 0
\end{bmatrix*}.
$$
### 5.3.1 Properties of Scalar-Matrix Multiplication
- $(\beta A)^T=\beta(A^T)$
- $(\beta + \gamma)A=\beta A + \gamma A$
- $(\beta \gamma)A=\beta(\gamma A)$
## 5.4 Matrix Norm
The norm of a $m\times n$ matrix $A$, denoted $\Vert A \Vert$, is the squareroot of the sum of the squares of its entries,
$$\Vert A \Vert = \sqrt{\sum_{i=1}^m \sum_{j=1}^n A_{ij}^2}$$
The RMS values of the matrix entries can be calculated with $\Vert A \Vert / \sqrt{mn}$.

The matrix norm allows us to define the distance between two matrices as $\Vert A - B \Vert$.
### 5.4.1 Properties of Matrix Norm
- Nonnegative: $\Vert A \Vert \geq 0$.
- Definiteness: $\Vert A \Vert = 0$ if and only if $A=0$.
- Nonnegative Homogeneous: For any scalar $\gamma$ and $m \times n$ matrix $A$, we have $\Vert \gamma A \Vert = \vert \gamma \vert \Vert A \Vert$. 
- Triangle Inequality: $\Vert A + B \Vert \leq \Vert A \Vert + \Vert B \Vert$.
- $\Vert A \Vert = \Vert A^T \Vert$.
- $\Vert A \Vert ^2 = \Vert a_1 \Vert ^2 + \cdots + \Vert a_n \Vert ^2$, where $a_1, \dots, a_n$ are the columns of $A$. I.e., the squared norm of a matrix is the sum of the squared norms of its columns.
# 6 Matrix-Vector Multiplication
If $A$ is an $m\times n$ matrix and $x$ is an $n$-vector, then the matrix-vector product $y=Ax$ is the $m$-vector $y$ with elements
$$
y_i = \sum_{k=1}^n A_{ik}x_k = A_{i1}x_1 + \cdots + A_{in}x_n, \quad\quad i=1,\dots,m
$$
As a simple example, we have
$$
\begin{bmatrix*}[r]
0 & 2 & -1 \\
-2 & 1 & 1
\end{bmatrix*} \begin{bmatrix*}[r]
2 \\ 1 \\ -1
\end{bmatrix*} = \begin{bmatrix*}[r]
(0)(2)+(2)(1)+(-1)(-1) \\
(-2)(2)+(1)(1)+(1)(-1)
\end{bmatrix*} = \begin{bmatrix*}[r]
3 \\ -4
\end{bmatrix*}
$$
## 6.1 Row and Column Interpretations
The matrix-vector product can be described in terms of the rows or columns of the matrix. From the equation above, we can see that $y_i$ is the inner product of $x$ with the $i$th row of $A$:
$$
y_i = b_i^Tx, \quad i=1,\dots,m,
$$
where $b_i^T$ is the row $i$ of $A$. It could also be interpreted in terms of the columns of $A$. If $a_k$ is the $k$th column of $A$, then $y=Ax$ can be written as 
$$
y=x_1a_1+x_2a_2 + \cdots + x_na_n.
$$
This shows that $y=Ax$ is a linear combination of the columns of $A$; the coefficients in the linear combination are the elements of $x$.
## 6.2 Properties of Matrix-Vector Multiplication
- For any $m \times n$ matrix $A$ and any $n$-vectors $u$ and $v$, we have $A(u+v)=Au+Av$.
- For any $m \times n$ matrices $A$ and $B$, and any $n$-vector $u$, we have $(A+B)u=Au + Bu$. 
- For any $m \times n$ matrix $A$, and any $n$-vector $u$, and any scalar $\alpha$, we have $(\alpha A)u=\alpha (Au)$. (This could be written as $\alpha A u$).
## 6.3 Input-Output Interpretation
We can interpret the relation $y=Ax$, with $A$ an $m \times n$ matrix, as a mapping from the $n$-vector $x$ to the $m$-vector $y$. In this case, $x$ would be the input, and $y$ would be the output.