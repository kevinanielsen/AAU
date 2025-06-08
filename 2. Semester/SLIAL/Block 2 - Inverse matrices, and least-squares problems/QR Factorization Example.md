# 2 x 2 Matrix
$$A = \begin{bmatrix*}[r]
1 & 2 \\ 3 & 4
\end{bmatrix*}$$
1. Compute
$$
\begin{aligned}
&q_1 = \frac{a_1}{\Vert a_1 \Vert}, &\Vert a_1 \Vert = \sqrt{1^2+3^2}=\sqrt{10}, &&q_1=\frac{1}{\sqrt{10}}\begin{bmatrix*}[r]
1 \\ 3
\end{bmatrix*}
\end{aligned}
$$
2. Project and subtract
$$
r_{12}=q_1^Ta_2=\frac{1 \cdot 2 + 3 \cdot 4}{\sqrt{10}}=\frac{14}{\sqrt{10}},
$$
$$
\tilde q_2=a_2-r_{12}q_1= \begin{bmatrix*}[r] 2 \\ 4 \end{bmatrix*} - \frac{14}{\sqrt{10}}\frac{1}{\sqrt{10}}\begin{bmatrix*}[r] 1 \\ 3 \end{bmatrix*} = \begin{bmatrix*}[r] 2 \\ 4 \end{bmatrix*} - \frac{14}{10}\begin{bmatrix*}[r]
1 \\ 3
\end{bmatrix*} = \begin{bmatrix*}[r]
2 - 1.4 \\ 4 - 4.2
\end{bmatrix*} = \begin{bmatrix*}[r]
0.6 \\ -0.2
\end{bmatrix*}
$$
3. Normalize
$$
r_{22}=\Vert \tilde q_2 \Vert = \sqrt{0.6^2+(-0.2)^2}=\sqrt{0.4}
$$
$$
q_2=\frac{\tilde q_2}{r_{22}}=\frac{1}{\sqrt{0.4}} \begin{bmatrix*}[r]
0.6 \\ -0.2
\end{bmatrix*} = \begin{bmatrix*}[r]
\frac{0.6}{\sqrt{0.4}} \\ \frac{0.2}{\sqrt{0.4}}
\end{bmatrix*}
$$
4. Assemble
$$
\begin{aligned}
&Q = \begin{bmatrix*}[r]
\frac{1}{\sqrt{10}} & \frac{0.6}{\sqrt{0.4}} \\
\frac{3}{\sqrt{10}} & \frac{0.2}{\sqrt{0.4}}
\end{bmatrix*}, & R = \begin{bmatrix*}
\sqrt{10} & \frac{14}{\sqrt{10}} \\ 0 & \sqrt{0.4}
\end{bmatrix*}
\end{aligned}
$$
# 4 x 4 Matrix
$$
\begin{aligned}
q_1 = \frac{a_1}{\Vert a_1 \Vert} = \begin{bmatrix}
0 \\ 1 \\ 0 \\ 0
\end{bmatrix}, &&r_{11} = \Vert a_1 \Vert = 1, &&r_{12} = q_1^Ta_2 = 0 
\end{aligned}
$$
$$
\begin{aligned}
\tilde q_2 = a_2-r_{12}q_1= \begin{bmatrix}
0 \\ 0 \\ 1 \\ 0
\end{bmatrix}, &&r_{22} = \Vert \tilde q_2 \Vert = 1, &&q_2=\frac{\tilde q_2}{r_{22}} = \begin{bmatrix}
0 \\ 0 \\ 1 \\ 0
\end{bmatrix}
\end{aligned}
$$
$$
\begin{aligned}
r_{13}=q_1^Ta_3 = 0, &&r_{23}=q_2^Ta_3 = 1, &&\tilde q_3 = a_3-r_{13}q_1-r_{23}q_2 = \begin{bmatrix}
1 \\ 0 \\ 0 \\ 0
\end{bmatrix}, &&r_{33}=\Vert \tilde q_3 \Vert = 1, &&q_3 = \frac{\tilde q_3}{r_{33}} = \begin{bmatrix}
1 \\ 0 \\ 0 \\ 0
\end{bmatrix}
\end{aligned}
$$
$$
\begin{aligned}
r_{14}=q_1^Ta_4=0, && r_{24}=q_2^Ta_4=0, &&r_{34} = q_3^Ta_4= 0
\end{aligned}
$$
$$
\begin{aligned}
\tilde q_4 = a_4-r_{14}q_1 - r_{24}q_2 - r_{34}q_3 = \begin{bmatrix}
0 \\ 0 \\ 0 \\ 1
\end{bmatrix}, &&r_{44}=\Vert \tilde q_4 \Vert = 1, && q_4=\frac{\tilde q_4}{r_{44}} =  \begin{bmatrix}
0 \\ 0 \\ 0 \\ 1
\end{bmatrix}
\end{aligned}
$$
$$
\begin{aligned}
Q = \begin{bmatrix}
0 & 0 & 1 & 0 \\ 
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 0 & 0 & 1 \\
\end{bmatrix}, &&R = \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{bmatrix}
\end{aligned}
$$