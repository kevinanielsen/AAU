Sometimes called linear programming.
# 1 Linear Programming Models
A manufacturer produces tables and chairs. The production requires two different pieces of raw material: large and small pieces. A table requires two of each, while the chair requires one large and two small pieces. The table is sold for 1600 SEK, while the chair sells for 1000 SEK. There are only 6 large and 8 small pieces available.

In order to develop a linear programming model for the manufacturing problem we introduce the following variables:
$$
\begin{align}
x_1 &=\text{number of tables manufactured and sold,} \\
x_2 &= \text{number of chairs manufactured and sold,} \\
z &= \text{total income.}
\end{align}
$$
The variable $z$ will be defined by the variables $x_1, x_2$. The income from each product is given by the price of the product multiplied by the number of products sold. The total income is
$$
z=1600x_1 + 1000x_2
$$
Given that we produce $x_1$ tables and $x_2$ chairs the required number of large pieces is $2x_1+x_2$ (tables cost 2 large, while chairs cost 1), and the required number of small pieces is $2x_1+2x_2$. Since only 6 large and 8 small are available, we must have that
$$
\begin{aligned}
2x_1+x_2 &\leq 6, \\
2x_1+2x_2 &\leq 8.
\end{aligned}
$$
Furthermore, it is impossible to produce a negative number of chairs or tables, which gives that
$$x_1,x_2 \geq 0.$$
Since we want to maximise the total income, and we know our income function and the restraints, we get the following linear programming model:
$$
\begin{aligned}
\text{maximize} \quad & z = 1600x_1 + 1000x_2 \\
\text{subject to} \quad & 2x_1 + x_2 \leq 6, \\
                        & 2x_1 + 2x_2 \leq 8, \\
                        & x_1,\, x_2 \geq 0.
\end{aligned}
$$
## 1.1 Graphical Solutions
A graphical solution can be done to the problem above. This is done by using the y-axis to show the values for $x_2$ and the x-axis to show the values for $x_1$. Next, we can show the constraints by finding variables for $x_1$ and $x_2$, which we do by inserting 0 for one variable and calculating the value of the other. 
We can do this for the first constraint by
$$
\begin{align}
2x_1+ 0 = 6 &\Rightarrow x_1=3, \quad x_2=0 \\
2\cdot 0 +x_2=6 &\Rightarrow x_1=0 \quad x_2=6
\end{align}
$$
This gives us two dots, from which we can draw a line between. Since we know by the constraint that the value has to be below 6, then we can gray out the area *above* this line. The same operations can be done for the second constraint, and for the last non-negative constraint, we know that the area has to be in the upper-right quadrant.
![[31467.png]]
We now know that the optimal solution to the optimization problem to be within the marked area.

To find the optimal solution, we draw a line, perpendicular to the total income vector $(1600, 1000)$, and move that line until we (hopefully) find a single maxima in the area.
![[65227.png]]
In this case, we ended up with the optimal solution being 2 chairs and 2 tables resulting in an income of
$$
1600\cdot2 + 1000\cdot 2 =5200 \text{ SEK}
$$
# 2 Standard Form
$$
\begin{aligned}
\text{minimize} \quad & z = \mathbf{c}^\top \mathbf{x}, \\
\text{subject to} \quad & A\mathbf{x} = \mathbf{b}, \\
& \mathbf{x} \geq \mathbf{0}
\end{aligned}
$$
- Min and not max
- Only = constraints
- All variables are nonnegative
- The right hand side is nonnegative
All linear optimization problems can be converted to standard form.

## Objective Function
Constant terms in the objective function will not change the set of optimal solutions and can therefore be eliminated. If the objective is to
$$
\text{maximize } z = c^Tx
$$
then change the objective function so that the objective becomes
$$
\text{minimize } \tilde z:=-z=-c^Tx.
$$
I.e. Convert a maximization problem to a minimization problem by multiplying your cost vector by -1
## Inequality Constraints and Negative Right-Hand Sides
Consider the inequality constraint
$$a^Tx \leq b,$$
By introducing a non-negative *slack variable* $s$ this constraint can be written as
$$
\begin{align}
a^Tx + s &= b, \\
s &\geq 0,
\end{align}
$$
which has the desired form of an equation.
Likewise, a constraint of the form
$$a^Tx \geq b,$$
can be written as
$$
\begin{align}
a^Tx-s&=b, \\
s &\geq 0.
\end{align}
$$
We call such variables $s$ *surplus variables*.
## Unrestricted and Non-Positive Variables
In a linear program
$$
\begin{aligned}
\text{minimize} \quad & z = c^T x, \\
\text{subject to} \quad & Ax = b, \\
& x_2 \leq 0, \\
& x_j \geq 0, \quad j = 3, \ldots, n,
\end{aligned}
$$
The $x_2$-variable can be replaced by the non-negative variables $\tilde x_2:=-x_2$.
The $x_1$-variable can be transformed into the difference of two non-negative variables. Namely, introduce the variables $x^+_1 \geq 0$ and $x^-_1 \geq 0$ and let $x_1=x^+_1-x^-_1$. Substituting $x_1$ with $x^+_1-x^-_1$ wherever it occurs transforms the problem into standard form.
# 3 Primal-Dual Pair of Problems
If the primal is feasible and the dual is feasible, then the primal has an optimal solution.
If the dual is feasible then the primal cannot be unbounded.
## 3.1 Example
### 3.1.1 Prime problem:
$$
\begin{align}
\max \quad & 1600x_1+1000x_2 \\
\text{S.T.} \quad & 2x_1+x_2 \leq 6 \\
&2x_1+2x_2 \leq 8 \\
&x_1 \geq 0, x_2 \geq 0
\end{align}
$$
Converting to standard form:
$$
\begin{align}
\min \quad &-1600x_1-1000x_2 \\
\text{S.T.} \quad &2x_1+x_2+S_1=6 \\
&2x_1+2x_2+S_2=8 \\
&x_1,x_2,S_1,S_2 \geq 0
\end{align}
$$
$$
C=\begin{pmatrix}
-1600 \\
-1000 \\
0 \\
0
\end{pmatrix}, \quad
b = \begin{pmatrix} 6 \\8 \end{pmatrix}, \quad
A=\begin{pmatrix}
2 \quad 1 \quad1 \quad 0 \\
2 \quad 2 \quad 0 \quad 1
\end{pmatrix}
$$
### 3.1.2 Dual problem:
$$
\begin{align}
\max \quad &\begin{pmatrix}6 \\ 8\end{pmatrix}^T\begin{pmatrix} y_1 \\ y_2\end{pmatrix} \\\\
\text{S.T.} \quad &\begin{pmatrix} 2 & 2 \\ 1 & 2 \\ 1 & 0 \\ 0 & 1 \end{pmatrix}\begin{pmatrix}y_1 \\ y_2\end{pmatrix} \leq \begin{pmatrix} -1600 \\ -1000 \\ 0 \\ 0 \end{pmatrix}
\end{align}
$$
In more human readable form
$$
\begin{align}
\max &&6y_1 + 8y_2 \\
\text{S.T.} && 2y_1+2y_2 \leq -1600 \\
&& y_1 + 2y_2 \leq -1000 \\
&& y_1 \leq 0 \\
&& y_2 \leq 0
\end{align}
$$
# Inbox
The feasible set can be denoted by:
$$
\mathcal{F} = \{x \in \mathbb{R}^n:Ax=b,x \geq 0\}
$$
Feasible solution: $x \in \mathcal{F}$
(Optimal) Solution: $\bar x \in \mathcal{F}$ such that
$$
c^T\bar x = \min c^Tx
$$

The linear optimization problem has 3 outcomes:
1. The problem is infeasible (i.e., $\mathcal{F} = \emptyset$)
2. The problem is unbounded
3. The problem has at least one optimal solution