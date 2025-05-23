# Compute the approximate solution for 
$$
\begin{aligned}
&A = \begin{bmatrix*}[r]
3 & -6 \\ 4 & -8 \\ 0 & 1
\end{bmatrix*}, &b= \begin{bmatrix*}[r]
-1 \\ 7 \\ 2
\end{bmatrix*}
\end{aligned}
$$
1. Compute the QR factorization
$$
\begin{aligned}
\Vert a_1 \Vert = \sqrt{3^2+4^2+0^2}=5, && q_1= \begin{bmatrix*}[r]
\frac35 \\ \frac45 \\ 0
\end{bmatrix*}
\end{aligned}
$$
$$
\begin{aligned}
r_{12}=q_1^Ta_2=\frac35(-6)+\frac45(-8)+0(1)=-\frac{18}5-\frac{32}5=-10
\end{aligned}
$$
$$
\begin{aligned}
\tilde q_2=a_2-r_{12}q_1 = \begin{bmatrix*}[r]
-6 \\ -8 \\ 1
\end{bmatrix*}-\left(-10 \begin{bmatrix*}
\frac35 \\ \frac 45 \\ 0
\end{bmatrix*}\right)= \begin{bmatrix*}[r]
-6 \\ -8 \\ 1
\end{bmatrix*}- \begin{bmatrix*}[r]
-6 \\ -8 \\ 0
\end{bmatrix*}= \begin{bmatrix*}[r]
0 \\ 0 \\ 1
\end{bmatrix*}
\end{aligned}
$$
$$
r_{22}=\Vert \tilde q_2 \Vert = \sqrt{0^2+0^2+1^2}=1
$$
$$
q_2=\frac{\tilde q_2}{r_{22}}= \begin{bmatrix*}[r]
0 \\ 0 \\ 1
\end{bmatrix*}
$$
$$
\begin{aligned}
Q = \begin{bmatrix*}[r]
\frac35 & 0 \\ \frac45 & 0 \\ 0 & 1
\end{bmatrix*}, &&R = \begin{bmatrix*}[r]
5 & -10 \\
0 & 1
\end{bmatrix*}
\end{aligned}
$$
2. Compute $Q^Tb$.
$$
Q^Tb = \begin{bmatrix*}
3/5 & 4/5 & 0 \\ 0 & 0 & 1
\end{bmatrix*} \begin{bmatrix*}[r]
-1 \\ 7 \\ 2
\end{bmatrix*} = \begin{bmatrix*}
5 \\ 2
\end{bmatrix*}
$$
3. Back substitution to solve $R \hat x = Q^Tb$
$i=2$
$$
\begin{aligned}
0x_1+1x_2=2 \Longrightarrow x_2=2
\end{aligned}
$$
$i=1$
$$
5x_1+(-10)x_2=5 \Longrightarrow 5x_1-20=5 \Longrightarrow 5x_1=25 \Longrightarrow x_1=5
$$
$$
\hat x = \begin{bmatrix*}[r]
5 \\ 2
\end{bmatrix*}
$$
[]()