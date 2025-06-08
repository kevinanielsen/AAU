**Literature:** AEP sections 7.1-7.3, 8.1-8.2.1
# 1 Introduction
## 1.1 The Manufacturing Problem
A manufacturer produces two pieces of furniture: tables and chairs. A table costs two large and two small pieces. A chair costs one large and two small. The manufacturer only has 6 large and 8 small pieces. A table is sold for 1600 while a chair sells for 1000. 

To maximize the total income, what should he produce?
## 1.2 A Linear Programming Model
We introduce the following variables:
$$
\begin{aligned}
x_1 &= \text{number of tables manufactured and sold}, \\
x_2 &= \text{number of chairs manufactured and sold}, \\
z &= \text{total income}.
\end{aligned}
$$
The variable $z$ is not a variable, but will be defined by the variables $x_1$ and $x_2$.

The total income is
$$z = 1600x_1+1000x_2.$$
Given that we produce $x_1$ tables and $x_2$ chairs the required number of large pieces is $2x_1 + x_2$ and the required number of small pieces is $2x_1+2x_2$. But we only have 6 large pieces and 8 small pieces, so we must have
$$
\begin{aligned}
2x_1+x_2 &\leq 6, \\
2x_1+2x_2 &\leq 8.
\end{aligned}
$$
Further, it is impossible to produce a negative number of products so
$$x_1, x_2 \geq 0.$$
Now that we have the constraints, the objective is to maximize the total income, so if we combine the income function and the constraints we get the following model:
$$
\begin{array}{l l r}
\text{maximize}   &z=&1600x_1&+1000x_2,\\
\text{subject to}&&2x_1&+x_2&\le6,\\
                 &&2x_1&+2x_2&\le8,\\
                 &&x_1,&x_2&\ge0.
\end{array}
$$

## 1.3 Graphical Solution
![[linear_opt_graphical_solution.png]]
# 2 Models
## 2.1 Standard Form
A linear programming problem in standard form is a problem of the form
minimize:
$z=\mathbf{c}^T\mathbf x,$
subject to:
$\mathbf{Ax}= \mathbf b$
$\mathbf x \ge \mathbf{0}^n$
where $\mathbf A \in R^{m \times n}$ and $\mathbf b \ge \mathbf 0 ^m$.
### 2.1.1 Objective Function
If the objective function is to maximize, then it can be converted to standard form by multiplying by -1.
$$
\text{maximize }z=\mathbf c^T \mathbf x,
$$
can be changed to
$$
\text{minimize } \tilde z:=-z=- \mathbf c^T \mathbf x
$$
I.e.,
$$
[\text{maximum value of }z]=-[\text{minimum vlaue of }\tilde z]
$$
## 2.2 Inequality Constraints and Negative Right-Hand Sides
Consider the inequality constraint
$$a^Tx\le b,$$
where $a \in \mathbb{R}^n$ and $b \in \mathbb R$. By introducing a non-negative slack variable $s$ this constraint can be written as
$$
\begin{align}
a^Tx+s&=b, \\
s &\ge 0.
\end{align}
$$
Suppose that $b<0$, then we would subtract by the slack variable to convert
$$a^Tx \ge b$$
into 
$$
\begin{aligned}
a^Tx-s&=b,\\
s &\ge 0.
\end{aligned}
$$

Using the manufacturing problem from earlier as an example, we would change from
maximize: $z=1600x_1+1000x_2,$ 
subject to:
$$
\begin{aligned}
2x_1+x_2+s_1&=6,\\
2x_1+2x_2+s_2&=8, \\
x_1,x_2,s_1,s_2 &\ge 0.
\end{aligned}
$$
## 2.3 Unrestricted and Non-Positive Variables
Consider the linear program
Minimize:
$z=c^Tx$,
subject to:
$$
\begin{aligned}
x_2 &\le 0, \\
x_j &\ge 0, \quad j=3, \dots, n,
\end{aligned}
$$
which is assumed to be in standard form except for the unrestricted variable $x_1$ and the non-positive variable $x_2$. 

The $x_2$-variable can be replaced by the non-negative variable $\tilde x_2 := -x_2$.
The $x_1$-variable can be transformed into the difference of two non-negative variables. Namely introduce the variables $x_1^+\ge0$ and $x_1^- \ge 0$ and let $x_1=x_1^+-x_1^-$.

Substituting $x_1$ with $x_1^+-x_1^-$ wherever it occurs transforms the problem into standard form. The drawback is that often the resulting problem is numerically unstable.
## 2.4 Example
Consider the linear program
maximize $z=9x_1-7x_2+3y_1,$
subject to 
$$
\begin{array}{r}
\text{maximize}& z=9x_1&-7x_2&+3y_1,&\\
\text{subject to}
&3x_1& +2x_2& -y_1 &\le 1, \\
&4x_1& -x_2& +2y_1 &\ge 3, \\
&x_1,& x_2 &&\ge0.
\end{array}
$$
In order to transform the objective function into the minimization form, let
$$
\tilde z := -z = -9x_1+7x_2-3y_1
$$
Further, by introducing the slack variable $s_1$ and the surplus variable $s_2$ the constraints can be transformed into an equality form by
$$
\begin{array}{r}
3x_1&+x_2&-y_1&+s_1&&=1,\\
4x_1& -x_2&+y_1&&-s_2&=3, \\
x_1,&x_2,&&s_1,&s_2&\ge 0.
\end{array}
$$
Finally, by introducing the variables $y_1^+,y_1^-$ we can handle the unrestricted variable $y_1$ by substituting it by $y_1^+-y_1^-$ whenever it occurs. We arrive at the standard form to
$$
\begin{array}{lr}
\text{minimze}
& \tilde z = -9x_1& +7x_2& -3y_1^+&+3y_1^-, \\
\text{subject to}
&3x_1& +x_2& -y_1^+ &+y_1^-&+s_1&&=1, \\
&4x_1&-x_2&+2y_1^+&-2y_1^-&&-s_2&=3, \\
&x_1,&x_2,&y_1^+,&y_1^-,&s_1,&s_2&\ge 0.
\end{array}
$$
# Feasible Set and Solution
Feasible set:
$$
\mathcal{F}=\{x \in \mathbb{R}^n:Ax=b, x\ge0 \}
$$
Feasible solution: $x \in \mathcal{F}$
(Optimal) Solution: $\bar x \in \mathcal F$ such that
$$
c^T \bar x = \min_{x\in \mathcal{F}}c^Tx
$$
# Alternatives
1. The problem is infeasible (i.e., $\mathcal{F}=\emptyset$). This happens when constraints are too "limiting"
2. The problem is unbounded. This happens if there is no lower bound for minimization problems or if there is no upper bounds for the maximization problem.
3. The problem has at least one optimal solution.

If the problem is formulated in the standard form, and it has solutions, at least one of them is "a corner" (extreme point) of the feasible set $\mathcal F$. 