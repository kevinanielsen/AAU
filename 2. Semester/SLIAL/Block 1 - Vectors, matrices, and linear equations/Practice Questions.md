# Gram-Schmidt Orthogonalization
[[K02 - Linear Independence#5 Gram-Schmidt Algorithm|Gram-Schmidt Algorithm]]
$$
\tilde q_i = a_i - \sum_{j=1}^{i-1}(q_j^Ta_i)q_j
$$
## Practice Problem 1: Two vectors in $\mathbb{R}^2$

Orthogonalize (and then normalize) the pair  
$$
a_1 = \begin{bmatrix}1\\1\end{bmatrix}, 
\quad
a_2 = \begin{bmatrix}2\\0\end{bmatrix}.
$$
## Practice Problem 1: Two vectors in $\mathbb{R}^2$

Orthogonalize (and then normalize) the pair  
$$
a_1 = \begin{bmatrix}1\\1\end{bmatrix}, 
\quad
a_2 = \begin{bmatrix}2\\0\end{bmatrix}.
$$

$$
\begin{aligned}
\tilde q_1 &= a_1 
= \begin{bmatrix*}[r]1 \\ 1\end{bmatrix*}, 
\quad
q_1 = \frac{\tilde q_1}{\|\tilde q_1\|} 
= \frac{1}{\sqrt{1^2 + 1^2}}
  \begin{bmatrix*}[r]1 \\ 1\end{bmatrix*}
= \frac{1}{\sqrt2}\begin{bmatrix*}[r]1 \\ 1\end{bmatrix*}.\\\\
\text{Then }q_1^T a_2 &= 
\begin{bmatrix}1/\sqrt2 & 1/\sqrt2\end{bmatrix}
\begin{bmatrix}2\\0\end{bmatrix}
= \frac{2}{\sqrt2}
= \sqrt2,\\\\
\tilde q_2 &= a_2 - (q_1^T a_2)\,q_1
= \begin{bmatrix*}[r]2 \\ 0\end{bmatrix*}
  - \sqrt2\cdot\frac{1}{\sqrt2}\begin{bmatrix*}[r]1 \\ 1\end{bmatrix*}
= \begin{bmatrix*}[r]2 \\ 0\end{bmatrix*}
  - \begin{bmatrix*}[r]1 \\ 1\end{bmatrix*}
= \begin{bmatrix*}[r]1 \\ -1\end{bmatrix*},\\\\
q_2 &= \frac{\tilde q_2}{\|\tilde q_2\|}
= \frac{1}{\sqrt{1^2 + (-1)^2}}
  \begin{bmatrix*}[r]1 \\ -1\end{bmatrix*}
= \frac{1}{\sqrt2}\begin{bmatrix*}[r]1 \\ -1\end{bmatrix*}.
\end{aligned}
$$

You will compute:
1. $\tilde q_1 = a_1$, then $q_1 = \dfrac{\tilde q_1}{\|\tilde q_1\|}$.
2. $\displaystyle \tilde q_2 = a_2 - (q_1^T a_2)\,q_1$, then $q_2 = \dfrac{\tilde q_2}{\|\tilde q_2\|}$.

---

## Practice Problem 2: Three vectors in $\mathbb{R}^3$

Orthogonalize (and normalize) the triple  
$$
a_1 = \begin{bmatrix}1\\0\\1\end{bmatrix},
\quad
a_2 = \begin{bmatrix}1\\1\\0\end{bmatrix},
\quad
a_3 = \begin{bmatrix}0\\1\\1\end{bmatrix}.
$$
$$ 
\begin{align}
\tilde q_1 &= \begin{bmatrix*}[r]
1 \\ 0 \\ 1
\end{bmatrix*} \\\\
q_1 &= \begin{bmatrix*}[r]
1 \\ 0 \\ 1
\end{bmatrix*} / \left( \sqrt{1^2 + 0^2 +1^2} \right) = \frac{1}{\sqrt2} \begin{bmatrix*}[r]
1 \\ 0 \\ 1
\end{bmatrix*} \\\\
\tilde q_2 &= \begin{bmatrix*}[r]
1 \\ 1 \\ 0
\end{bmatrix*} - (\begin{bmatrix*}[r] \frac{1}{\sqrt2} & 0 & \frac{1}{\sqrt2}\end{bmatrix*}^T \begin{bmatrix*}[r] 1 \\ 1 \\ 0 \end{bmatrix*})\begin{bmatrix*} \frac{1}{\sqrt2} \\ 0 \\ \frac{1}{\sqrt2} \end{bmatrix*}\\ &= \begin{bmatrix*}[r] 1 \\ 1 \\ 0 \end{bmatrix*} -\left(\frac{1}{\sqrt2}\right)\begin{bmatrix*} \frac{1}{\sqrt2} \\ 0 \\ \frac{1}{\sqrt2} \end{bmatrix*} = \begin{bmatrix*} 0.5 \\ 1 \\ -0.5 \end{bmatrix*} \\\\
q_2 &= \begin{bmatrix*} 0.5 \\ 1 \\ -0.5 \end{bmatrix*} /\left( \sqrt{0.5^2 + 1^2 + (-0.5)^2} \right) \\ &=\begin{bmatrix*} 0.5 \\ 1 \\ -0.5 \end{bmatrix*}/\sqrt{1.5} = \frac{1}{\sqrt{1.5}}\begin{bmatrix*} 0.5 \\ 1 \\ -0.5 \end{bmatrix*} \\\\
\tilde q_3 &= \begin{bmatrix*}[r] 0 \\ 1 \\ 1 \end{bmatrix*} - \left(\begin{bmatrix*}[r] \frac{1}{\sqrt2} & 0 & \frac{1}{\sqrt2} \end{bmatrix*}^T \begin{bmatrix*}[r] 0 \\1\\1 \end{bmatrix*}\right)\begin{bmatrix*} \frac{1}{\sqrt2} \\ 0 \\ \frac{1}{\sqrt2} \end{bmatrix*} 
-
\left(\begin{bmatrix*}[r] \frac{1}{2\sqrt{1.5}} & \frac{1}{\sqrt{1.5}} & \frac{-1}{2\sqrt{1.5}}\end{bmatrix*}^T \begin{bmatrix*}[r] 0 \\1\\1 \end{bmatrix*}\right)\begin{bmatrix*} \frac{1}{2\sqrt{1.5}} \\ \frac{1}{\sqrt{1.5}} \\ \frac{-1}{2\sqrt{1.5}}\end{bmatrix*} \\
&= \begin{bmatrix*}[r] 0 \\ 1 \\ 1 \end{bmatrix*} - \left(\frac{1}{\sqrt2}\right)\begin{bmatrix*} 0.5 \\ 0 \\0.5 \end{bmatrix*} - \left(\frac{1}{2\sqrt{1.5}}\right)\begin{bmatrix*} \frac{1}{2\sqrt{1.5}} \\ \frac{1}{\sqrt{1.5}} \\ \frac{-1}{2\sqrt{1.5}}\end{bmatrix*} \\
&= \begin{bmatrix*}[r] 0 \\ 1 \\ 1 \end{bmatrix*} - \begin{bmatrix*} \frac{1}{2\sqrt2} \\ 0 \\ \frac{1}{2\sqrt2} \end{bmatrix*} - \begin{bmatrix*} \frac{1}{6} \\ \frac{1}{3} \\ \frac{-1}{6} \end{bmatrix*}
\end{align}
$$
You will compute:
1. $\tilde q_1 = a_1$, then $q_1 = \dfrac{\tilde q_1}{\|\tilde q_1\|}$.
2. $\displaystyle \tilde q_2 = a_2 - (q_1^T a_2)\,q_1$, then $q_2 = \dfrac{\tilde q_2}{\|\tilde q_2\|}$.
3. $\displaystyle \tilde q_3 = a_3 - (q_1^T a_3)\,q_1 - (q_2^T a_3)\,q_2$, then $q_3 = \dfrac{\tilde q_3}{\|\tilde q_3\|}$.


# Matrix-Vector Multiplication
1. Compute $Ax$ for  
$$
A = \begin{bmatrix}
3 & 1 \\
-2 & 4
\end{bmatrix},
\quad
x = \begin{bmatrix}2 \\ -3\end{bmatrix}.
$$
$$
Ax = \begin{bmatrix*}[r]
3(2)+1(-3) \\
-2(2)+4(-3)
\end{bmatrix*} = \begin{bmatrix*}[r]
3 \\ -16
\end{bmatrix*}
$$
2. Compute $Ax$ for  
$$
A = \begin{bmatrix}
0 & 5 & -1 \\
2 & -3 & 4
\end{bmatrix},
\quad
x = \begin{bmatrix}1 \\ 0 \\ 2\end{bmatrix}.
$$
$$
Ax= \begin{bmatrix*}[r]
0(1)+5(0)+(-1)(2) \\
2(1)+(-3)(0)+4(2)
\end{bmatrix*} = \begin{bmatrix*}[r]
-2 \\ 10
\end{bmatrix*}
$$
3. Compute $Ax$ for  
$$
A = \begin{bmatrix}
1 & -1 & 0 \\
0 & 2 & 3 \\
4 & 0 & -2
\end{bmatrix},
\quad
x = \begin{bmatrix}-1 \\ 2 \\ 1\end{bmatrix}.
$$
$$
\begin{bmatrix*}[r]
1(-1)+(-1)(-2)+0(1) \\
0(-1)+2(2)+3(1) \\
4(-1)+0(2)+(-2)(1)
\end{bmatrix*} = \begin{bmatrix*}[r]
-3 \\ 7 \\ -6
\end{bmatrix*}
$$
4. Compute $Ax$ for  
$$
A = \begin{bmatrix}
2 & 0 & 1 & -1 \\
-1 & 3 & 2 & 0
\end{bmatrix},
\quad
x = \begin{bmatrix}0 \\ 4 \\ -2 \\ 1\end{bmatrix}.
$$
$$
Ax = \begin{bmatrix*}[r]
2(0) + 0(4) + 1(-2) + -1(1) \\
-1(0)+3(4)+2(-2)+0(1)
\end{bmatrix*} = \begin{bmatrix*}[r]
-3 \\ 8
\end{bmatrix*}
$$
5. Compute $Ax$ for  
$$
A = \begin{bmatrix}
5 & -2 & 0 \\
1 & 1 & 1 \\
-3 & 4 & 2 \\
2 & 0 & -1
\end{bmatrix},
\quad
x = \begin{bmatrix}3 \\ -1 \\ 2\end{bmatrix}.
$$
$$
Ax = \begin{bmatrix*}[r]
5(3)+(-2)(-1)+0(2) \\
1(3)+1(-1)+1(2) \\
-3(3)+4(-1)+2(2) \\
2(3)+0(-1)+(-1)(2)
\end{bmatrix*} = \begin{bmatrix*}[r]
17 \\ 4 \\ -9 \\ 4
\end{bmatrix*}
$$
# Matrix Transposing
1. Compute $A^T$ for
$$A = \begin{bmatrix}
1 & -2 & 3\\
0 & 5 & -1
\end{bmatrix}$$
$$
A^T = \begin{bmatrix*}[r]
1 & 0 \\
-2 & 5 \\
3 & -1
\end{bmatrix*}
$$
2. Compute $B^T$ for
$$B = \begin{bmatrix}
4 & 0 & -3\\
2 & 7 & 1\\
-5 & 8 & 6
\end{bmatrix}$$
$$
B^T = \begin{bmatrix*}[r]
4 & 2 & -5 \\
0 & 7 & 8 \\
-3 & 1 & 6
\end{bmatrix*}
$$
3. Compute $C^T$ for 
$$C = \begin{bmatrix}
9 & -4\\
1 & 2\\
-3 & 7\\
0 & 5
\end{bmatrix}$$
$$
C^T = \begin{bmatrix*}[r]
9 & 1 & -3 & 0 \\
-4 & 2 & 7 & 5
\end{bmatrix*}
$$
4. Compute $D^T$ for
$$D = \begin{bmatrix}
1 & 2 & 3 & 4 & 5\\
6 & 7 & 8 & 9 & 10\\
-1 & -2 & -3 & -4 & -5\\
0 & 11 & 12 & 13 & 14\\
15 & 16 & 17 & 18 & 19
\end{bmatrix}$$
$$
D^T = \begin{bmatrix*}[r]
1 & 6 & -1 & 0 & 15 \\
2 & 7 & -2 & 11 & 16 \\
3 & 8 & -3 & 12 & 17 \\
4 & 9 & -4 & 13 & 18 \\
5 & 10 & -5 & 14 & 19
\end{bmatrix*}
$$
5. Compute $E^T$ for
$$E = \begin{bmatrix}
2 & -1 & 0 & 3\\
4 & 5 & -2 & 1\\
-6 & 7 & 8 & 9
\end{bmatrix}$$
$$
E^T = \begin{bmatrix*}[r]
2 & 4 & -6 \\
-1 & 5 & 7 \\
0 & -2 & 8 \\
3 & 1 & 9
\end{bmatrix*}
$$
# Frobenius Norm
1. Compute the Frobenius norm of  
$$
A = \begin{pmatrix}
2 & -1\\
0 & 3
\end{pmatrix}.
$$
$$
\Vert A \Vert = \sqrt{2^2+(-1)^2+0^2+3^2}=\sqrt{4+1+9}=\sqrt{14}
$$
2. Compute the Frobenius norm of  
$$
B = \begin{pmatrix}
1 & 2 & 2\\
-3 & 0 & 4
\end{pmatrix}.
$$
$$
\Vert B \Vert = \sqrt{1^2+2^2+2^2+(-3)^2+0^2+4^2} = \sqrt{1+4+4+9+16} = \sqrt{34}
$$
3. Compute the Frobenius norm of  
$$
C = \begin{pmatrix}
-1 & -1 & -1\\
-1 & -1 & -1\\
-1 & -1 & -1
\end{pmatrix}.
$$
$$
\Vert C \Vert = \sqrt{(-1)^2 \cdot 9}=\sqrt{9}=3
$$
4. Compute the Frobenius norm of  
$$
D = \begin{pmatrix}
5 & 0 & 0\\
0 & -5 & 0\\
0 & 0 & 5
\end{pmatrix}.
$$
$$
\Vert D \Vert = \sqrt{5^2 + (-5)^2 + 5^2}=\sqrt{75}
$$