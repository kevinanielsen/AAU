# 1 Literature
Chapter 10
# 2 Matrix-Matrix Multiplication
Two matrices with compatible dimensions can be multiplied. Their dimensions are compatible if the number of columns of $A$ equals the number of rows of $B$. Suppose $A$ and $B$ are compatible, e.g., $A$ has a size of $m \times p$ and $B$ has size $p \times n$. Then the product matrix $C = AB$ is the $m \times n$ matrix with elements
$$
C_{ij}=\sum_{k=1}^p A_{ik}B_{kj}=A_{i1}B_{1j}+\cdots+A_{ip}B_{pj}, \quad\quad i = 1, \dots, m, \quad j=1,\dots,n.
$$
I.e., moving left to right along the $i$th row of $A$, while moving top to bottom down the $j$th column of $B$. 
$$
\begin{bmatrix*}[r]
-1.5 & 3 & 2 \\ 1 & -1 & 0
\end{bmatrix*} \begin{bmatrix*}[r]
-1 & -1 \\ 0 & -2 \\ 1 & 0
\end{bmatrix*} = \begin{bmatrix*}[r]
3.5 & -4.5 \\ -1 & 1
\end{bmatrix*}
$$
$$ 
\begin{align}
(1,1)&=-1.5(-1)+3(0)+2(1)&&=3.5 \\
(1,2)&=-1.5(-1)+3(-2)+2(0)&&=-4.5 \\
(2,1)&=1(-1)+(-1)(0)+0(1)&&=-1 \\
(2,2)&=1(-1)+(-1)(-2)+0(0)&&=1
\end{align}
$$

Order matters in matrix multiplication, meaning that it is in general **not** commutative, i.e., we do not have $AB=BA$. Furthermore, $BA$ might not be possible even if $AB$ is, the only way both could work is if both matrices are square.
## 2.1 Properties of Matrix Multiplication
- Associativity: $(AB)C=A(BC)$. We can just write $ABC$.
- Associativity with scalar multiplication: $\gamma(AB)=(\gamma A)B=A(\gamma B)$ 
- Distributivity with addition: Matrix multiplication distributes across matrix addition: $A(B+C)=AB+AC$ and $(A+B)C=AC+BC$. Note that matrix multiplication has higher precedence than addition, so $AC+BC$ is interpreted as $(AC)+(BC)$.
- Transpose of product: The transpose of a product is the product of the transposes, but in the opposite order: $(AB)^T=B^TA^T$.
## 2.2 Products of Block Matrices
$$
\begin{bmatrix*}[r]
A & B \\ C & D
\end{bmatrix*} \begin{bmatrix*}[r]
E & F \\ G & H
\end{bmatrix*} = \begin{bmatrix*}[r]
AE+BG & AF + BH \\
CE + DG & CF + DH
\end{bmatrix*},
$$
for any matrices $A, B, \dots, H$ for which the matrix products above make sense. This formula is the same as the formula for multiplying two $2 \times 2$ matrices.
## 2.3 Gram Matrix
For an $m \times n$ matrix $A$, with columns $a_1, \dots, a_n$, the matrix product $G=A^TA$ is called the Gram matrix. The gram matrix can be expressed as
$$
G = A^TA= \begin{bmatrix*}
a_1^Ta_1 & a_1^Ta_2 & \cdots & a_1^Ta_n \\
a_2^Ta_1 & a_2^Ta_2 & \cdots & a_2^Ta_n \\
\vdots & \vdots & \ddots & \vdots \\
a_n^Ta_1 & a_n^Ta_2 & \cdots & a_n^Ta_n \\
\end{bmatrix*}
$$
# 3 Composition of Linear Functions
## 3.1 Matrix-Matrix Products and Composition
Suppose $A$ is an $m \times p$ matrix and $B$ is $p \times n$. We can associate with these matrices two linear functions $f:\mathbf{R}^p \to \mathbf{R}^m$ and $g:\mathbf R^n \to \mathbf R ^p$, defined as $f(x)=Ax$ and $g(x)=Bx$. The composition of the two functions is the function $h: \mathbf R^n \to \mathbf R^m$ with
$$h(x)=f(g(x))=A(Bx)=(AB)x.$$
# 4 Matrix Power
A square matrix $A$ multiplied by it self forms $AA$, which we refer to as $A^2$. If $k$ is a positive integer, then $k$ copies of $A$ multiplied together is denoted $A^k$. If $k$ and $l$ are positive integers, and $A$ is square, then $A^kA^l=A^{k+l}$ and $(A^k)^l=A^{kl}$. By convention we take $A^0=I$

If $A$ is not square, it cannot be multiplied by itself, i.e., it cannot be raised to a power of 2 or more.
# 5 QR Factorization
## 5.1 Matrices With Orthonormal Columns
A square matrix that satisfies $A^TA=I$ is called orthogonal; Its columns are an orthonormal basis.
## 5.2 Norm, Inner Product, and Angle Properties
Suppose the columns of the $m \times n$ matrix $A$ are orthonormal, and $x$ and $y$ are any $n$-vectors. We let $f:\mathbf R^n \to \mathbf R^m$ be the function that maps $z$ to $Az$. Then we have the following:
- $\Vert Ax \Vert = \Vert x \Vert$. $f$ is norm preserving
- $(Ax)^T(Ay)=x^Ty$. $f$ preserves the inner product between vectors
- $\angle (Ax, Ay)=\angle(x,y)$. $f$ also preserves angles between vectors.
## 5.3 QR Factorization
- Running [[K02 - Linear Independence#5 Gram-Schmidt Algorithm|Gram-Schmidt]] on columns $a_1, \dots, a_k$ of $n \times k$ matrix $A$
- If columns are linearly independent, get orthonormal $q_1, \dots, q_k$
- Define $n\times k$ matrix $Q$ with columns $q_1, \dots, q_k$
- $Q^TQ=I$
$R_{ij}=q_i^Ta_j$ and $R_{ii}=\Vert \tilde q_i \Vert$
So, $QR$ factorization of $A$ is a way of describing the matrix $A$ as a product of two matrices, $Q$ and $R$. 