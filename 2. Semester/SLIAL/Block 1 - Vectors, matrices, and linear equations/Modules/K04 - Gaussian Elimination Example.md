Consider the tableau
$$
\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & \vert & -7 \\
0 & 2 & 4 & -6 & \vert & -6 \\
0 & 0 & 0 & -5 &\vert & 0 \\
0 & 0 & 0 & 0 &\vert & 0 \\
\end{bmatrix*}
$$
Column 3 is not a pivot column, meaning that it corresponds with a free variable.

The last column is not a pivot column, so the system is consistent (there are solutions). There are three pivot columns, and one free variable (there are many solutions). Let us ignore the zero rows, and rename the variables as $(z_1,z_2,z_3)=(x_1,x_2,x_4)$ and the free variable $y_1=x_3$. We get a system:
$$
\left\{
\begin{align}
z_1+4z_2-9z_3 &= -6-5y_1 \\
2z_2-6z_3 &= -6 -4y_1 \\
-5z_3 &= 0
\end{align}
\right.
$$
From the last equation:
$$z_3=0$$
from the second equation:
$$ 
\begin{align}
2z_2-6z_3&=-6-4y_1 \\
\Rightarrow2z_2-6\cdot0&=-6-4y_1 \\
\Rightarrow 2z_2&=-6-4y_1\\
\Rightarrow z_2 &= -3-2y_1
\end{align}
$$
Finally, from the first equation:
$$ 
\begin{align}
&z_1+4z_2-9z_3&=-6-5y_1 \\
\Rightarrow &z_1+4(-3-2y_1)-9(0)&=-6-5y_1 \\
\Rightarrow &z_1-12-8y_1&=-6-5y_1 \\
\Rightarrow &z_1=6+3y_1
\end{align}
$$
We can now return to the original variables:
$$
\begin{bmatrix*}[r]
x_1 \\ x_2 \\ x_3 \\ x_4
\end{bmatrix*} = \begin{bmatrix*}[r]
z_1 \\ z_2 \\ y_1 \\ z_3
\end{bmatrix*} = \begin{bmatrix*}
5+3y_1 \\ -3-2y_1 \\ y_1 \\ 0
\end{bmatrix*} = \begin{bmatrix*}[r]
5 \\ -3 \\ 0 \\ 0
\end{bmatrix*} + y_1 \begin{bmatrix*}[r]
3 \\ -2 \\ 1 \\ 0
\end{bmatrix*}
$$
where $y_1$ is a free variable (in general, there may be more than one). Thus, we have a parametric description of infinitely many solutions to our linear system.