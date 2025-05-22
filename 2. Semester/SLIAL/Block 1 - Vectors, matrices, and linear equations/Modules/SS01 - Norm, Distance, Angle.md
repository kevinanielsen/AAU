# 1 Literature
Chapter 3
# 2 Norm
The Euclidean norm of an $n$-vector $x$, denoted $\Vert x \Vert$, is the squareroot of the sum of the squares of its elements,
$$
\Vert x \Vert = \sqrt{x_1^2+x_2^2+\cdots + x_n^2}
$$
It can also be expressed as the squareroot of the [[K01 - Introduction, Vectors, Linearity#5 Inner Product|inner product]] of the vector itself, i.e., $\Vert x \Vert = \sqrt{x^Tx}$.
$$
\left\Vert \begin{bmatrix} 
2 \\ -1 \\ 2
\end{bmatrix} \right\Vert = \sqrt{2^2+-1^2+2^2}=\sqrt{4+1+4}=\sqrt{9}=3
$$
$$\left\Vert \begin{bmatrix} 
0 \\ -1
\end{bmatrix} \right\Vert = 1.$$
When $x$ is a scalar, i.e., a 1-vector, the Euclidean norm is the same as the absolute value of $x$. 
## 2.1 Properties of Norm
- Nonnegative homogeneity: $\Vert \beta x \Vert = \vert \beta \vert \Vert x \Vert$. Multiplying a vector by a scalar multiplies the norm by the absolute value of the scalar.
- Triangle inequality: $\Vert x + y \Vert \leq \Vert x \Vert + \Vert y \Vert$. The Euclidean norm of a sum of two vectors is no more than the sum of their norms.
- Nonnegativity: $\Vert x \Vert \geq 0$.
- Definiteness: $\Vert x \Vert = 0$ only if $x = 0$.
The last two properties together, stating that the norm is always nonnegative, and zero only when the vector is zero, are called positive definiteness. 
## 2.2 Root-Mean-Square Value
The norm is related to the root-mean-square (RMS) value of an $n$-vector $x$ defined as
$$\mathbf{rms} (x) = \sqrt{\frac{x_1^2 + \cdots + x_n^2}{n}}=\frac{\Vert x \Vert}{\sqrt{n}}$$
The argument of the squareroot in the middle expression is called the mean square value of $x$, denoted $\mathbf{ms}(x)$, and the RMS value is the squareroot of the mean square value. The RMS value of a vector $x$ is useful when comparing norms of vectors with different dimensions. The RMS value tells us what the 'typical' value of $\vert x_i \vert$ is.
## 2.3 Norm of a Sum
The norm of the sum of two vectors $x$ and $y$ can be calculated with
$$\Vert x + y \Vert = \sqrt{\Vert x \Vert ^2 + 2x^Ty + \Vert y \Vert ^2}.$$
## 2.4 Norm of Block Vectors
The norm-squared of a stacked vector is the sum of the norm-squared values of its subvectors e.g. with $d=(a,b,c)$, we have
$$\Vert d \Vert ^2 = d^Td = a^Ta+b^b+c^Tc=\Vert a \Vert^2 + \Vert b \Vert^2 + \Vert c \Vert^2.$$
This can be written in terms of norms as
$$
\Vert (a,b,c) \Vert = \sqrt{\Vert a \Vert^2+\Vert b \Vert^2+\Vert c \Vert^2} = \Vert (\Vert a \Vert, \Vert b \Vert, \Vert c \Vert)\Vert.
$$
In words: The norm of a block vector is the norm of the vector formed from the norms of the subvectors. The right-hand side of the equation above: The outer norm symbols enclose a 3-vector, with (scalar) entries $\Vert a \Vert, \Vert b \Vert$, and $\Vert c \Vert$.
## 2.5 Chebyshev Inequality
Suppose that $x$ is an $n$-vector, and that $k$ of its entries satisfy $\vert x_i \vert \geq a$, where $a > 0$. Then $k$ of its entries satisfy $x_i^2 \geq a^2$. It follows that
$$\Vert x \Vert ^2 = x_1^2+ \cdots + x_n^2 \geq ka^2,$$
since $k$ of the numbers in the sum are at least $a^2$, and the other $n-k$ numbers are nonnegative. We can conclude that $k \leq \Vert x \Vert ^2 / a^2$, which is called the Chebyshev Inequality. When $\Vert x \Vert ^2 / a^2 \geq n$, the inequality tells us nothing, since we always have  $k \leq n$. For $a > \Vert x \Vert$, the inequality is $k \leq \Vert x \Vert ^2/a^2 < 1$, so we conclude that $k=0$. In other words, no entry of a vector can be larger in magnitude than the norm of the vector. The Chebyshev inequality is easier to interpret in terms of the RMS value of a vector. We can write it as
$$
\frac{k}{n} \leq \left( \frac{\mathbf{rms}(x)}{a} \right)^2,
$$
where $k$ is, as above, the number of entries of $x$ with absolute value at least $a$. 
# 3 Distance
## 3.1 Euclidean Distance
We can use the norm to define the Euclidean distance between two vectors $a$ and $b$ as the norm of their difference:
$$\mathbf{dist} (a,b) = \Vert a - b \Vert.$$
For one, two and three dimensions, this distance is exactly the usual distance between points with coordinates $a$ and $b$.

If $a$ and $b$ are $n$-vectors, we refer to the RMS value of the difference, $\Vert a-b \Vert / \sqrt n$, as the RMS deviation between the two vectors.

$$ 
\begin{align}
&u = \begin{bmatrix} 
1.8 \\ 2.0 \\ -3.7 \\ 4.7
\end{bmatrix}, &v = \begin{bmatrix} 
0.6 \\ 2.1 \\ 1.9 \\ -1.4
\end{bmatrix}, &&w = \begin{bmatrix} 
2.0 \\ 1.9 \\ -4.0 \\ 4.6
\end{bmatrix}.
\end{align}
$$
The distances between pairs of them are
$$ 
\begin{align}
&\Vert u-v \Vert = 8.368, &\Vert u - w \vert = 0.387, &&\Vert v - w \Vert = 8.533.
\end{align}
$$
The Euclidean distance can be calculated using the inner product with
$$ 
\begin{align}
\Vert a-b \Vert^2 &= (a-b)^T(a-b) \\
\Vert a-b \Vert^2 &= a^Ta-2a^Tb+b^Tb \\
\mathbf{dist}(a,b)&= \sqrt{a^Ta-2a^Tb+b^Tb}
\end{align}
$$
## 3.2 Triangle Inequality
Consider a triangle in two or three dimensions, whose vertices have coordinates $a,b,c$. The lengths of the sides are the distances between the vertices,
$$
\begin{aligned}
&\mathbf{dist}(a,b)=\Vert a-b \Vert, &\mathbf{dist}(b,c)=\Vert b-c \Vert, &&\mathbf{dist}(a,c)=\Vert a-c \Vert.
\end{aligned}
$$
Geometric intuition tells us that the length of any side of a triangle cannot exceed the sum of the lengths of the other two sides. For example, we have
$$\Vert a - c \Vert \leq \Vert a - b \Vert + \Vert b - c \Vert.$$
This follows from the triangle inequality, since
$$\Vert a - c \Vert = \Vert (a-b) + (b-c) \Vert \leq \Vert a-b\Vert + \Vert b-c\Vert.$$
# 4 Standard Deviation
For any vector $x$, the vector $\tilde x = x - \mathbf{avg}(x)\mathbf1$ is called the associated de-meaned vector, obtained by subtracting from each entry of $x$ the mean value of the entries. The mean value of the entries of $\tilde x$ is zero, i.e., $\mathbf{avg}(\tilde x)=0$. This explains why $\tilde x$ is called the de-meaned version of $x$; it is $x$ with its mean removed. It is useful for understanding how the entries of a vector deviate from their mean value. It is zero if all the entries of $x$ are the same.

The standard deviation of an $n$-vector $x$ is defined as the RMS value of the de-meaned vector $x-\mathbf{avg}(x)\mathbf{1}$, i.e.,
$$
\mathbf{std}(x)=\sqrt{\frac{(x_1-\mathbf{avg}(x))^2 + \cdots + (x_n-\mathbf{avg}(x))^2}{n}}
$$
It can be written using the inner product and norm as
$$
\mathbf{std}(x)=\frac{\Vert x - (\mathbf1^Tx/n)\mathbf1\Vert}{\sqrt{n}}.
$$
The standard deviation of a vector $x$ tells us the typical amount by which its entries deviate from their average value. The standard deviation is zero only when all its entries are equal. It is small when the entries are nearly the same.
If $x=(1,-2,3,2)$ then we have
$$
\begin{aligned}
\mathbf{std}(1,-2,3,2)&=\frac{\Vert(1,-2,3,2)-(((1,1,1,1)^T(1,-2,3,2))/4)(1,1,1,1)\Vert}{\sqrt 4} \\\\
&= \frac{\Vert(1,-2,3,2)-(4/4)(1,1,1,1)\Vert}{\sqrt 4} \\\\
&= \frac{\Vert(0, -3, 2, 1)\Vert}{\sqrt 4} = \frac{\sqrt{0^2+(-3)^2+2^2+1^2}}{2} = \frac{\sqrt{14}}{2}\approx 1.871
\end{aligned}
$$
## 4.1 Average, RMS, and Standard Deviation
The average, RMS, and standard deviation of a vector are related by the formula
$$
\mathbf{rms}(x)^2=\mathbf{avg}(x)^2+\mathbf{std}(x)^2.
$$
## 4.2 Properties of Standard Deviation
- Adding a constant: For any vector $x$ and any number $a$, we have $\mathbf{std}(x+a\mathbf{1})=\mathbf{std}(x)$. Adding a constant to every entry of a vector does not change its standard deviation.
- Multiplying by a scalar: For any vector $x$ and any number $a$, we have $\mathbf{std}(ax)=\vert a \vert \mathbf{std}(x)$. Multiplying a vector by a scalar multiplies th standard deviation by the absolute value of the scalar.
## 4.3 Standardization
For any vector $x$, we refer to $\tilde x = x - \mathbf{avg}(x)\mathbf{1}$ as the de-meaned version of $x$, since it has average or mean value zero. If we then divide by the RMS value of $\tilde x$ (which is the standard deviation of $x$), we obtain the vector
$$
z = \frac{1}{\mathbf{std}(x)}(x-\mathbf{avg}(x)\mathbf{1}).
$$
This vector is called the standardized version of $x$. It has mean zero, and standard deviation one. Its entries are sometimes called the $z$-scores associated with the original entries of $x$. For example, $z_4=1.4$ means that $x_4$ is 1.4 standard deviations above the mean of the entries of $x$.
# 5 Angle
## 5.1 Cauchy-Schwarz Inequality
An important inequality that relates norms and inner products:
$$\vert a^Tb \vert \leq \Vert a \Vert \Vert b \Vert$$
for any $n$-vectors $a$ and $b$. Written out in terms of the entries, this is
$$
\vert a_1b_1+\cdots a_nb_n \vert \leq (a_1^2 + \cdots a_n^2)^{1/2}(b_1^2+ \cdots + b_n^2)^{1/2}
$$
## 5.2 Verification of Triangle Inequality
We can use the Cauchy-Schwarz inequality to verify the triangle inequality. Let $a$ and $b$ be any vectors. Then
$$ 
\begin{align}
\Vert a+b \Vert &= \Vert a \Vert^2 + 2a^Tb + \Vert b \Vert ^2 \\
&\leq \Vert a \Vert^2 + 2\Vert a \Vert \Vert b \Vert + \Vert b \Vert ^2
\end{align}
$$
where we used the Cauchy-Schwarz inequality in the second line. Taking the squareroot we get the triangle inequality, $\Vert a + b \Vert \leq \Vert a \Vert + \Vert b \Vert$.
## 5.3 Angle Between Vectors
The angle between two nonzero vectors $a,b$ is defined as
$$\theta=\arccos\left(\frac{a^Tb}{\Vert a \Vert \Vert b \Vert}\right)$$
where arccos denotes the inverse cosine, normalized to lie in the interval $[0, \pi]$. In other words, we define $\theta$ as the unique number between 0 and $\pi$ that satisfies
$$a^Tb=\Vert a \Vert\Vert b \Vert \cos \theta.$$
The angle between $a$ and $b$ is written as $\angle (a,b)$, and is sometimes expressed in degrees.

With vectors $a=(1,2,-1)$ and $b=(2,0,-3)$ we have
$$
\arccos\left(\frac{5}{\sqrt{6} \sqrt{13}}\right)=\arccos(0.5661)=0.9690=55.52^\circ
$$
The angle is a symmetric function of $a$ and $b$: we have $\angle(a,b)=\angle(b,a)$. The angle is not affected by scaling each of the vectors by a positive scalar: We have, for any vectors $a,b$, and any positive numbers $\alpha a,\beta b$,
$$\angle(\alpha a, \beta, b)=\angle(a,b).$$
## 5.4 Acute and Obtuse Angles
Angles are classified according to the sign of $a^Tb$. Suppose $a$ and $b$ are nonzero vectors of the same size.
- If the angle is $\pi/2$, i.e. $a^Tb=0$, the vectors are said to be orthogonal, and we write $a \perp b$. By convention, we say that a zero vector is orthogonal to any vector.
- If the angle is zero, i.e., $a^Tb=\Vert a \Vert \Vert b \Vert$, the vectors are aligned. Each vector is a positive multiple of the other.
- If the angle is $\pi=180^\circ$, which means $a^Tb=-\Vert a \Vert \Vert b \Vert, the vectors are anti-aligned. Each vector is a negative multiple of the other.
- If $\angle(a,b) < \pi/2=90^\circ$, the vectors are said to make an acute angle. This is the same as $a^Tb > 0$, i.e., the vectors have positive inner product.
- If $\angle (a,b) > \pi/2=90^\circ$, the vectors are said to make an obtuse angle. This is the same as $a^Tb < 0$, i.e., the vectors have negative inner product.

## 5.5 Norm of Sum via Angles
- If $x$ and $y$ are aligned $(\theta = 0)$, we have $\Vert x + y \Vert = \Vert x \Vert + \Vert y \Vert$. Thus, their norms add.
- If $x$ and $y$ are orthogonal $(\theta = 90 ^ \circ)$, we have $\Vert x + y \Vert ^2 = \Vert x \Vert^2 + \Vert y \Vert^2$. Thus, their norm-squared values add, and we have $\Vert x + y \Vert = \sqrt{\Vert x \Vert^2 + \Vert y \Vert^2}$ (Pythagorean theorem).
## 5.6 Correlation Coefficient
Suppose $a$ and $b$ are $n$-vectors, with associated de-meaned vectors
$$
\begin{aligned}
&\tilde a = a - \mathbf{avg}(a)\mathbf{1}, &\tilde b=b-\mathbf{avg}(b)\mathbf{1}.
\end{aligned}
$$
Assuming these de-meaned vectors are not zero, i.e., the entries of the vectors are not all equal, we define their correlation coefficient as
$$
\rho = \frac{\tilde a ^T \tilde b}{\Vert \tilde a \Vert \Vert \tilde b \Vert}.
$$
Thus, $\rho = \cos \theta$, where $\theta = \angle(\tilde a, \tilde b)$. We can also express the correlation coefficient in terms of the vectrs $u$ and $v$ obtained by standardizing $a$ and $b$. With $u=\tilde a / \mathbf{std}(a)$ and $v=\tilde b/ \mathbf{std}(b)$, we have
$$\rho = u^Tv/n.$$
The Cauchy-Schwarz inequality tells us that the correlation coefficient ranges between -1 and +1. For this reason, the correlation coefficient is sometimes expressed as a percentage. When $\rho = 0$, we say the vectors are uncorrelated. $\rho = 1$ only occurs if the vectors $\tilde a$ and $\tilde b$ are aligned. Likewise, $\rho = -1$ only occurs when $\tilde a$ and $\tilde b$ are negative multiples of each other.