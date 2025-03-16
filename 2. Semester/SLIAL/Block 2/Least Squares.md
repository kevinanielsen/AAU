# Least Squares Problem
Suppose that the $m \times x$ matrix $A$ is tall, so the system of linear equations $Ax = b$, where $b$ is an $m$-vector, is over-determined, meaning that there are more equations ($m$) than variables to choose ($n$). These equations have a solution only if $b$ is a linear combination of the columns of $A$.

For most choices of $b$ there is no $n$-vector $x$ for which $Ax=b$. As a compromise, we seek an $x$ for which $r=Ax-b$, which is called the *residual* (for the equations $Ax=b$), is as small as possible. This suggests that we should choose x so as to minimize the norm of the residual, $\lVert Ax−b \rVert$. If we find an $x$ for which the residual vector is small, we have $Ax \approx b$, i.e., $x$ almost satisfies the linear equations $Ax=b$ 

If asked to solve a linear equation at the exam, show the normal equation and do (portion elimination??). 

**When to use normal equations vs QR factorization?**
Typically it is best to use QR factorization to solve least square problems.

