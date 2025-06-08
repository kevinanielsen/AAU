# Example 1
## Primal
$$
\begin{array}{lrrl}
\text{maximize} &4x_1&+3x_2 \\
\text{subject to} &2x_1&+1x_2 &\le 100\\
&1x_1&+2x_2 &\le 80\\
&x_1, &x_2, &\ge0
\end{array}
$$
## Dual
$$
\begin{array}{lrrl}
\text{minimize} &100y_1&+80y_2 \\
\text{subject to} &2y_1&+1y_2 &\ge4 \\
&1y_1 &+2y_2 &\ge3 \\
&y_1, &y_2 &\ge0
\end{array}
$$
# Example from lecturer
Primal problem P:
$$
\begin{array}{lrrl}
\text{maximize} &2x_1&+3x_2 \\
\text{subject to} &3x_1&+2x_2&\le12, \\
&x_1&+2x_2&\le8, \\
&x_1&+x_2&\le4.5, \\
&x_1, &x_2&\ge0.
\end{array}
$$
Its standard form (also called P):
$$
\begin{array}{lrrl}
\text{minimize} &-2x_1&-3x_2 \\
\text{subject to} &3x_1 &+2x_2&+s_1&=12, \\
&x_1&+2x_2&+s_2 &=8, \\
&x_1&+x_2&+s_3&=4.5, \\
&x\ge0, &s\ge0.
\end{array}\\
$$
$$
\begin{array}{rl}
\text{minimize} &\begin{bmatrix*}
-2 \\ -3 \\ 0 \\ 0\\ 0
\end{bmatrix*}^T \begin{bmatrix*}[r]
x_1 \\ x_2 \\ s_1 \\ s_2 \\ s_3
\end{bmatrix*} \\
\text{subject to}\\ 
&\begin{bmatrix*}[r]
3 & 2 & 1 & 0 & 0 \\
1 & 2 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 & 1 \\
\end{bmatrix*}
\begin{bmatrix*}[r]
x_1 \\ x_2 \\ s_1 \\ s_2 \\ s_3
\end{bmatrix*} = \begin{bmatrix*}[r]
12 \\ 8 \\ 4.5
\end{bmatrix*}
\end{array}
$$
Dual problem P*:
$$
\begin{array}{rl}
&\text{maximize} &\begin{bmatrix*}
12 \\ 8 \\ 4.5
\end{bmatrix*}^T \begin{bmatrix*}
y_1 \\ y_2 \\ y_3
\end{bmatrix*} \\
&\text{subject to} \\
&&\begin{bmatrix*}
3 & 1 & 1 \\
2 & 2 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix*} \begin{bmatrix*}
y_1 \\ y_2 \\ y_3
\end{bmatrix*} \le \begin{bmatrix*}
-2 \\ -3 \\ 0 \\ 0 \\ 0
\end{bmatrix*}
\end{array}
$$
$$
\begin{array}{ll}
\text{maximize} & 12y_1 + 8y_2 + 4.5y_3\\
\text{subject to} \\
&3y_1 + y_2 + y_3 \le -2, \\
&2y_1+2y_2 +y_3 \le -3, \\
&y_1 \le0 \\
&y_2 \le0 \\
&y_3 \le0
\end{array}
$$