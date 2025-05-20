# 1 Literature 
Chapter 8 + Slides
# 2 Linear and Affine Functions
The notation $f:\mathbf{R}^n \to \mathbf{R}^m$ means that $f$ isa. function that maps real $n$-vectors to real $m$-vectors. The value of the function $f$, evaluated at an $n$-vector $x$, is an $m$-vector $f(x)=(f_1(x), f_2(x), \dots, f_m(x))$. Each of the components $f_i$ of $f$ is itself a scalar-valued function of $x$.
## 2.1 The Matrix-Vector Product Function
Suppose $A$ is an $m \times n$ matrix. We can define a function $f:\mathbf{R}^n \to \mathbf{R}^m$ by $f(x)=Ax$. 
## 2.2 Superposition and Linearity
The function $f:\mathbf{R}^n \to \mathbf{R}^m$, defined by $f(x)=Ax$, is linear, i.e., it satisfies the [[K01 - Introduction, Vectors, Linearity#6.3 Superposition And Linearity|superposition property]]:
$$
f(\alpha x + \beta y)=\alpha f(x)+\beta f(y)
$$
holds for all $n$-vectors $x, y$ and all scalars $\alpha, \beta$.

We can verify that superposition holds for $f$ using properties of [[Matrices#3.5 Matrix-Vector multiplication|matrix-vector]] and [[K01 - Introduction, Vectors, Linearity#4 Scalar-Vector Multiplication|scalar-vector]] multiplication:
$$
\begin{aligned}
f(\alpha x + \beta y) &= A(\alpha x + \beta y) \\
&= A(\alpha x) + A(\beta y) \\
&= \alpha(Ax) + \beta(Ay) \\
&=\alpha f(x) + \beta f(y)
\end{aligned}
$$
### 2.2.1 Examples of Linear Functions
- Negation: $f$ changes the sign of $x$: $f(x)=-x$.
Negation can be expressed as $f(x)=Ax$ with $A=-I$.
- Reversal: $f$ reverses the order of the elements of $x$: $f(x)=(x_n, x_{n-1}, \dots, x_1)$.
The reversal function can be expressed as $f(x)=Ax$ with 
$$
A = \begin{bmatrix*}[r]
0 & \cdots & 0 & 1 \\
0 & \cdots & 1 & 0 \\
\vdots & \ddots &\vdots & \vdots \\
1 &\cdots & 0 &0
\end{bmatrix*}.
$$
- Running sum: $f$ forms ths running sum of the elements in $x$:
$$
f(x)=(x_1, x_1+x_2, x_1 + x_2 + x_3, \dots, x_1 + x_2 + \cdots + x_n).
$$
The running sum function can be expressed as $f(x)=Ax$ with
$$
A = \begin{bmatrix*}[r]
1 & 0 & \cdots & 0 & 0 \\
1 & 1 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
1 & 1 & \cdots & 1 & 0 \\
1 & 1 & \cdots & 1 & 1 \\
\end{bmatrix*},
$$
i.e., $A_{ij}=1$ if $i \geq j$ and $A_{ij}=0$ otherwise.
- De-meaning: $f$ subtracts the mean from each entry of a vector $x$: $f(x) = x - \mathbf{avg}(x) \mathbf{1}$. 
The de-meaning function can be expressed as $f(x)=Ax$ with
$$A=\left[\begin{array}{cccc}1-1 / n & -1 / n & \cdots & -1 / n \\ -1 / n & 1-1 / n & \cdots & -1 / n \\ \vdots & \vdots & \ddots & \vdots \\ -1 / n & -1 / n & \cdots & 1-1 / n\end{array}\right].$$
### 2.2.2 Examples of Functions That Are Not Linear
- Absolute Value: $f$ replaces each element of $x$ with its absolute value: $f(x)=(\vert x_1 \vert, \vert x_2 \vert, \dots, \vert x_n \vert)$.
This function is not linear. For example, with $n=1, x=1, y=0,\alpha = -1, \beta = 0$, we have
$$f(\alpha x + \beta y)=1\neq \alpha f(x) + \beta f(y)=-1$$
so superposition does not hold.
## 2.3 Affine Functions
A vector-valued function $f:\mathbf{R}^n \to \mathbf{R}^m$ is called affine if it can be expressed as $f(x)=Ax+b$, where $A$ is an $m \times n$ matrix and $b$ is an $m$-vector. It can be shown that a function $f:\mathbf{R}^n \to \mathbf{R}^m$ is affine if and only if
$$
f(\alpha x + \beta y)=\alpha f(x)+\beta f(y)
$$
holds for all $n$-vectors $x, y$ and all scalars $\alpha, \beta$ that satisfy $\alpha + \beta = 1$.
# 3 Systems of Linear Equations
Consider a set (also called a system) of $m$ linear equations in $n$ variables or unknowns $x_1, \dots, x_n$:
$$
\begin{align}
A_{11}x_1+A_{12}x_2 + \cdots + A_{1n}x_n &= b_1 \\
A_{21}x_1+A_{22}x_2 + \cdots + A_{2n}x_n &= b_2 \\
&\;\; \vdots \\
A_{m1}x_1+A_{m2}x_2 + \cdots + A_{mn}x_n &= b_m \\
\end{align}
$$
The numbers $A_{ij}$ are called the coefficients in the linear equations, and the numbers $b_i$ are called the right-hand sides. These equations can be written succinctly in matrix notation as
$$Ax=b$$
In this context, the $m\times n$ matrix $A$ is called the coefficient matrix, and the $m$-vector $b$ is called the right-hand side. An $n$-vector $x$ is called a solution of the linear equations if $Ax=b$ holds. A set of linear equations can have no solutions, one solution or multiple solutions.
## 3.1 Examples
- The set of linear equations
$$
x_1+x_2=1, \quad x_1=-1, \quad x_1-x_2=0
$$
is written as $Ax=b$ with
$$
A= \begin{bmatrix*}[r]
1 & 1 \\ 1& 0 \\ 1 & -1
\end{bmatrix*}, \quad b = \begin{bmatrix*}[r]
1 \\ -1 \\ 0
\end{bmatrix*}.
$$
It has no solutions.
- The set of linear equations
- $$x_1+x_2=1, \quad x_2 + x_3 = 2$$
is written as $Ax=b$ with
$$
A = \begin{bmatrix*}[r]
1 & 1 & 0 \\ 0 & 1 & 1
\end{bmatrix*}, \quad b = \begin{bmatrix*}[r]
1 \\ 2
\end{bmatrix*}.
$$
It has multiple solutions, including $x=(1,0,2)$ and $x=(0,1,1)$.
## 3.2 Over-Determined and Under-Determined Systems of Linear Equations
The set of linear equations is called over-determined if $m>n$, under-determined if $m<n$, and square if $m=n$; these correspond to the coefficient matrix being tall, wide and square, respectively. 
When the system of linear equations is over-determined, there are more equations than variables or unknowns.
When the system of linear equations is under-determined, there are more unknowns than equations. 
When the system is square, the numbre of unknowns and equations is the same. A set of equations with zero right-hand side, $Ax=0$ is called a homogenous set of equations. Any homogeneous set of equations has $x=0$ as a solution.
# 4 Gaussian Elimination

## 4.1 Total Matrix
For the purpose of Gaussian elimination, it can be useful to combine $A$ and $b$ into a tableau / total matrix by adding $b$ as another column to $A$: $[A \vert b]$. 
### 4.1.1 Example 
System of equations:
$$
\begin{align}
x_1+2x_2-4x_3 &= 5 \\
6x_2+7x_3 &= 8 \\
10x_1-12x_3 &= 0
\end{align}
$$
Corresponding matrix-vector notation:
$$
\begin{bmatrix*}[r]
1 & 2 & -4 \\
0 & 6 & 7 \\
10 & 0 & -12
\end{bmatrix*} \begin{bmatrix*}[r]
x_1 \\ x_2 \\ x_3
\end{bmatrix*} = \begin{bmatrix*}[r]
5 \\ 8 \\ 0
\end{bmatrix*}
$$
Resulting tableau:
$$
\begin{bmatrix*}[r]
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
10 & 0 & -12 & \vert & 0
\end{bmatrix*}
$$
## 4.2 Row Echelon Form
**Leading Entry**: The leftmost nonzero entry in each row
A matrix is in row-echelon form if:
- All rows consisting of only zero entries are at the bottom of the matrix
- The leading entry of each nonzero row is to the right of the learding entry of every row above it.
### 4.2.1 Example
The following matrix is in the row echelon form. The leading entries are marked bold.  $*$ entries may be zero or nonzero
$$
\begin{bmatrix*}
\mathbf1 & * &* &* &* \\
0 & 0 & \mathbf3 &* &* \\
0 & 0 & 0 & \mathbf{-2} &* \\
0 & 0 & 0 & 0 & 0
\end{bmatrix*}
$$
## 4.3 Row Operations
The following three operations are allowed in Gaussian elimination:
- Scaling (multiplying or dividing) all elements in a matrix row with a nonzero number.
- Exchanging the positions of two matrix rows.
- Adding (or subtracting) a scaled row to/from another row.
All three operations are reversible, and do not change the set of solutions from the linear system.
### 4.3.1 Example
In order to eliminate the element in position $(3,1)$, we can multiply row one by 10 and subtract it from row 3:
$$
\begin{bmatrix*}[r]
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
10 & 0 & -12 & \vert & 0
\end{bmatrix*} \Longrightarrow \begin{bmatrix*}[r]
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
0 & -20 & -28 & \vert & -50
\end{bmatrix*}
$$
It's important to do it for all elements in the row, even the additional column originating from the right-hand side.

We can now focus on the last tableau, and eliminate the element in position $(3,2)$ by multiplying row 2 with $20/6=10/3$ and adding it to row 3:
$$
\begin{bmatrix*}[r]
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
0 & -20 & -28 & \vert & -50
\end{bmatrix*} \Longrightarrow \begin{bmatrix*}[r]
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
0 & 0 & 51\frac{1}{3} & \vert & -23 \frac{1}{3}
\end{bmatrix*}
$$
Now, the last tableau is in the row echelon form, with the leading elements $1,6,51\frac{1}{3}$. 
## 4.4 Pivot Columns
Pivot positions correspond to the leading entries in the row echelon form. Columns with pivot positions are called pivot columns
$$\begin{bmatrix*}
\mathbf1 & * &* &* &* \\
0 & 0 & \mathbf3 &* &* \\
0 & 0 & 0 & \mathbf{-2} &* \\
0 & 0 & 0 & 0 & 0
\end{bmatrix*}$$
In the table above, the pivot positions are: $(1,1), (2,3), (3,4)$, and the pivot columns are $1,3,4$.
## 4.5 Transformation to Row Echelon Form
1. Find the leftmost nonzero column. This is our pivot column.
The pivot position is at its top.
2. Select a nonzero entry in the pivot column. If necessary,
exchange rows to bring it to the pivot position.
3. Eliminate all entries under the pivot position by subtracting
the multiples of the top row from them.
4. Cover/ignore the row containing the current pivot position
and all the rows above it. Apply the algorithm recursively to
the remaining matrix.
### 4.5.1 [[K04 - Row Elimination Example]]
## 4.6 Existence of Solutions From Row Echelon Form
The system has solutions if and only if the last column is not a pivot column, i.e., if the last column is a pivot column, then the system has no solutions.
## 4.7 Uniqueness of Solutions From Row Echelon Form
Let $R$ be the row echelon form of the tableau $[A \vert b]$, and suppose that the system $Ax=b$ admits solutions.
1. The solution is unique if and only if each variable $x_i$ corresponds to a pivot column.
2. Assume that solutions exist, but there are variables $x_i$, which do not correspond to a pivot column. Such variables are called free variables. In this situation, there are infinitely many solutions.

To summarize:
- No solutions: The last column ($b$-column) is a pivot column.
- Unique (1) solution: Solution exists and all columns corresponding to variables are pivot columns.
![[Pasted image 20250519141600.png]]
- Infinitely many solutions: Solution exists and free variables.
## 4.8 Backward Substitution Algorithm
Assuming we have linear system with a solution and which we have converted to the row echelon form.

Starting with a case where all columns related to a variable are pivot columns (i.e., a system with a unique solution), we would like to solve the system:
$$
\left\{ \begin{array}{r}
R_{11}x_1+R_{12}x_2+\cdots+R_{1n}x_n &=c_1 \\
R_{22}x_2+\cdots+R_{2n}x_n &= c_2 \\
&\vdots\quad\; \\
R_{nn}x_n&=c_n
\end{array}
\right.
$$
- Solve the last equation: $x_n=c_n/R_{nn}$. We can divide, because $R_{nn} \neq 0$.
- Substitute the result into the previous equation:
$$
R_{n-1,n-1}x_{n-1}+R_{n-1,n}x_n=c_{n-1}
$$
can be solved for $x_{n-1}$:
$$
x_{n-1}=R_{n-1,n-1}^{-1}[c_{n-1}-R_{n-1,n}x_n] = \frac{1}{R_{n-1,n-1}}(c_{n-1}-R_{n-1,n}x_n)
$$
- Proceed like this all the way to equation 1.

The algorithm can be written as
For $i=n, n-1, \dots, 1$:
$$
x_i=R_{ii}^{-1} \left[ c_i-\sum_{j=i+1}^n R_{ij}x_j \right]
$$
### 4.8.1 Example
$$
\begin{bmatrix*}
1 & 2 & -4 & \vert & 5 \\
0 & 6 & 7 & \vert & 8 \\
0 & 0 & 51 \frac13 & \vert & -23 \frac13
\end{bmatrix*}
$$
from the last equation:
$$
x_3=\frac{-23\frac13}{51\frac13}=-\frac{5}{11}\approx-0.4545
$$
This can be used in the second equation
$$
x_2 \approx \frac{8+7\cdot \frac{5}{11}}{6}\approx 1.8636
$$
Finally, we substitute this into the first equation to compute
$$
x_1 \approx \frac{5-2\cdot1.8636-4\cdot0.4545}{1}\approx -0.5455
$$
## 4.9 Backward Substitution with Free Variables
- We ignore all the zero rows
- Let us relabel the variables and call the free variables $y_j, j=1, \dots, N_f$, and the remaining variables $z_j, j=1, \dots, N_p$. 
- Let us also move all the free variables into the right hand side.
After these manipulations, we arrive at the system:
$$
Rz=c-\sum_{j=1}^{N_f}d_jy_j,
$$
where $R$ is an upper-triangular matrix with non-zero diagonal. For each fixed values of $y_j$ we can run a backward substitution algorithm and compute the corresponding unique values of $z_j$; therefore the system has infinitely many solutions corresponding to the infinitely many 

### 4.9.1 [[K04 - Gaussian Elimination Example]]
