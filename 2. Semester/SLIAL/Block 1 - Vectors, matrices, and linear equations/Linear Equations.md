# 1 Linear and Affine Functions
## 1.1 Vector-Valued Functions of Vectors
The notation $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$ means that $f$ is a function that maps real $n$-vectors to real $m$-vectors. The value of the function $f$, evaluated at an $n$-vector $x$, is an $m$-vector $f(x)=(f_1(x), f_2(x), \dots, f_m(x))$. Each of the components $f_i$ of $f$ is itself a [[Vectors#4 Linear Functions#4.1 Notation|scalar-valued function]] of $x$. As with scalar-valued functions, we sometimes write $f(x)=f(x_1, x_2, \dots, x_n)$ to emphasize that $f$ is a function of $n$ scalar arguments. We write $f_i(x)=f_i(x_1,x_2,\dots,x_n)$ to emphasize that $f_i$ is a function mapping the scalar arguments $x_1,\dots,x_n$ into a scalar.

## 1.2 The Matrix-Vector Product Function
Suppose $A$ is an $m \times n$ matrix. We can define a function $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$ by $f(x)=Ax$. The [[Vectors#4.2 The Inner Product Function|inner product function]] is the special case with $m=1$.

## 1.3 Superposition and Linearity
The function $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$, defined by $f(x)=Ax$, is *linear*, i.e., it satisfies the [[Vectors#4.3 Superposition and Linearity|superposition property]]. We can verify that superposition holds for $f$ using properties of matrix-vector and scalar-vector multiplication:
$$
\begin{align}
f(\alpha x + \beta y) &= A(\alpha x + \beta y) \\
&= A(\alpha x) + A(\beta y) \\
&= \alpha(Ax)+ \beta(Ay) \\
&= \alpha(Ax) + \beta (Ay) \\
&= \alpha f(x) + \beta f(y)
\end{align}
$$
Thus, we can associate with every matrix $A$ a linear function $f(x)=Ax$.
If $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$ is a linear function, then there exists exactly one matrix $A$ such that $f(x)=Ax$ for all $x$.
## 1.4 Affine Functions
A vector-valued function $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$ is called affine if it can be expressed as $f(x)=Ax+b$, where $A$ is an $m\times n$ matrix and $b$ is an $m$-vector. It can be shown that a function $f:\mathbf{R}^n \rightarrow \mathbf{R}^m$ is affine if and only if
$$
f(\alpha x + \beta y) = \alpha f(x) + \beta f (y)
$$
holds for all $n$-vectors $x,y$, and all scalars $\alpha, \beta$ that satisfy $\alpha + \beta = 1$. In other words, superposition holds for affine combinations of vectors. For linear functions, superposition holds for any linear combination of vectors. 
We can find the parameters $A, b$ of an affine function by evaluating $f$ at the vectors $0, \; e_1, \dots, e_n$, where $e_k$ is the $k$th unit vector in $\mathbf{R}^n$. We have
$$
A= \left[ \; 
\begin{matrix} 
f(e_1)-f(0) & f(e_2)-f(0) &\cdots & f(e_n)-f(0)
\end{matrix} 
\; \right], \quad b = f(0)
$$
Affine vector-valued functions are often called linear, even though they are linear only when the vector $b$ is zero.
### 1.4.1 Example (in $\mathbf{R}^2$)
Suppose we have an affine function $f:\mathbf{R}^2 \to \mathbf{R}^2$. We know $f(x) = Ax + b$, where $A$ is a $2\times 2$ matrix and $b$ is a vector in $\mathbb{R}^2$. To find $b$, evaluate $f$ at the zero vector:
$$
f(0) = A\cdot 0 + b = b.
$$
For example, if $f(0) = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$, then $b = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$. 
Next, evaluate $f$ at the standard basis vectors $e_1$ and $e_2$.  Let 
$$
e_1 = \begin{pmatrix}1 \\ 0\end{pmatrix} \quad \text{and} \quad e_2 = \begin{pmatrix}0 \\ 1\end{pmatrix}.
$$
Suppose we find 
$$
f(e_1) = \begin{pmatrix}5 \\ 3\end{pmatrix} \quad \text{and} \quad f(e_2) = \begin{pmatrix}3 \\ 4\end{pmatrix}.
$$
Each column of $A$ is given by $f(e_k) - f(0)$: 
$$
\begin{aligned}
Ae_1 = f(e_1) - f(0) = \begin{pmatrix}5 \\ 3\end{pmatrix} - \begin{pmatrix}2 \\ 1\end{pmatrix} = \begin{pmatrix}3 \\ 2\end{pmatrix}, \\ \\
Ae_2 = f(e_2) - f(0) = \begin{pmatrix}3 \\ 4\end{pmatrix} - \begin{pmatrix}2 \\ 1\end{pmatrix} = \begin{pmatrix}1 \\ 3\end{pmatrix}. 
\end{aligned}
$$
Hence,
$$
A = \begin{pmatrix} 3 & 1 \\ 2 & 3 \end{pmatrix}, \quad b = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
$$
# 2 Linear Function Models
Functions or relations between variables that arise in natural science, engineering, and social sciences can be approximated as linear or affine functions. In these cases we refer to the linear function relating the two sets of variables as a model or an approximation, to remind us that the relation is only an approximation, and not exact.
## 2.1 Taylor Approximation
Suppose $f:\mathbf{R}^n \to \mathbf{R}^m$ is differentiable, i.e., has partial derivatives, and $z$ is an $n$-vector. The first-order Taylor approximation of $f$ near $z$ is given by
$$
\begin{align}
\hat{f}(x)_i &= f_i(z)+\frac{\partial f_i}{\partial x_1}(z)(x_1-z_1)+\cdots+ \frac{\partial f_i}{\partial x_n}(z)(x_n-z_n) \\
&= f_i(z)+\nabla f_i(z)^T(x-z)
\end{align}
$$
for $i=1, \dots, m$. For $x$ near $z$, $\hat{f}(x)$ is a very good approximation of $f(x)$. We can express this approximation in compact notation, using [[Matrices#3.5 Matrix-Vector multiplication|matrix-vector multiplication]], as
$$
\hat f(x) = f(z)+ Df(z)(x-z),
$$
where the $m \times n$ matrix $Df(z)$ is the *derivative* or *Jacobian* matrix of $f$ at $z$. Its components are the partial derivatives of $f$,
$$
Df(z)_{ij} = \frac{\partial f_i}{\partial x_j}(z), \quad i=1, \dots, m, \quad j=1,\dots,n,
$$
evaluated at the point $z$. The rows of the Jacobian are $\nabla f_i(z)^T$, for $i=1,\dots,m$. 

As in the scalar-valued case, Tayler approximation is sometimes written with a second argument as $\hat f (x;z)$ to show the point $z$ around which the approximation is made. Evidently, the Taylor series approximation $\hat f$ is an affine function of $x$. It is often called a linear approximation of $f$, though it is not, in general, a linear function.
