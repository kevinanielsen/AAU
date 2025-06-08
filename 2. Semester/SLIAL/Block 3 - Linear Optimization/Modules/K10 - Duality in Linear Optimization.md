**Literature:** AEP: sections 7.4-7.5, sections 10.2-10.3 (up and including Theorem 10.6 w/o proof, pp 243-248)
[[K09 - Introduction, Terminology, Standard Form#1.1 The Manufacturing Problem|The Manufacturing Problem]]
# 1 Sensitivity Analysis
Sensitivity analysis describes how the optimal solution changes if the data of the problem is changed. The three primary changes (made independently of each other) are discussed:
1. an increase in the number of large pieces available
2. an increase in the number of small pieces available
3. a decrease in the price of the tables
## 1.1 An Increase in the Number of Large Pieces Available
Assume that the number of large pieces available increases from 6 to 7. The linear program becomes
$$
\begin{array}{lr}
\text{maximize}&z=1600x_1&+1000x_2& \\
\text{subject to}&2x_1&+x_2 &\le 7,\\
&2x_1&+2x_2&\le8, \\
&x_1, &x_2 & \ge0.
\end{array}
$$
![[k10_increase_in_number_of_pieces_available.png]]

We see that the optimal solution becomes $(3, 1)^T$ and $z^* = 5800$, which means that an additional large piece increases the income by $5800-5200=600$. (the shadow price)
## 1.2 An Increase in the Number of Small Pieces Available
Starting from the original setup, in the same manner as for the large pieces, it follows from the figure above that two additional small pieces give the new optimal solution $x^*=(1,4)^T$ and $z^*=5600$. $(5600-5200)/2=200$, meaning the shadow price of the small pieces is 200. 
## 1.3 A Decrease in the Price of the Tables
Now assume that the price of tables is decreased from 1600 to 800. The new linear program becomes
$$
\begin{array}{r}
\text{maximize}&z=800x_1&+1000x_2, \\
\text{subject to}&2x_1&+x_2,&\le 6, \\
&2x_1 &+2x_2 &\le 8, \\
&x_1, &x_2 &\ge 0.
\end{array}
$$
![[k10_decrease_in_price_of_tables.png]]
The optimal solution is then $(0,4)^T$, that is, we will not produce any tables.
# 2 The Dual of the Manufacturing Problem
## 2.1 A Dual Problem
To study the problem of another manufacturer (billy) looking to acquire "our" resources, we introduce new variables:
$$
\begin{aligned}
y_1 &= \text{the price which Billy offers for each large piece.}\\
y_2 &= \text{the price which Billy offers for each small piece.} \\
w &= \text{the total bid which Billy offers.}
\end{aligned}
$$
In order to accept to sell, the price offered should be at least as high as the value that the resources represent in our optimal production plan. Considering the income on a table sold, it is 1600 for two large and two small pieces. The bid would then be too low unless $2y_1+2y_2 \ge 1600$. The corresponding requirement for the chairs is that $y_1 + 2y_2 \ge 1000$.

Billy is interested in minimizing the total bid, under the conditions that the offer is accepted. Observing that $y_1$ and $y_2$ are prices and therefore non-negative, we have the following mathematical model for Billy's problem:
$$
\begin{array}{lrrl}
\text{minimize} &w=6y_1&+8y_2, \\
\text{subject to}&2y_1&+2y_2, &\ge1600, \\
&y_1&+2y_2&\ge1000, \\
&y_1, &y_2 &\ge0.
\end{array}
$$
This is usually called the dual problem.

The optimal solution to this problem is $y^*=(600, 200)^T$, the total offer is $w^*=5200$. I.e. the optimal solution equals the shadow price of the resources.
# 3 The Linear Programming Dual
For every linear program it is possible to construct the Lagrangian dual problem through the Lagrangian relaxation of the affine constraints. We refer to this problem as the dual linear program.

One of the primal or dual problems may be easier to solve than the other.
## 3.1 Canonical Form
The canonical form is connected with the directions of the inequalities of the problem and the objective. If the objective is to maximize the objective function, then every inequality of type "$\le$" is said to be of canonical form. Similarly, if the objective is to minimize the objective function, then every inequality of type "$\ge$" is said to be of canonical form.
- $\ge$ for minimization problems.
- $\le$ for maximization problems.
## 3.2 Constructing the Dual
From the canonical form, we can construct the dual (D), to a linear program, (P), according to the following rules.
### 3.2.1 Dual Variables
To each constraint of (P) a dual variable, $y_i$, is introduced. If the $i$th constraint of (P) is an inequality of canonical form, then $y_i$ is a nonnegative variable, that is, $y_i \ge 0$. Similarly, if the $i$th constraint of (P) is an inequality that is not of canonical form, then $y_i \le 0$. Finally, if the $i$th constraint of (P) is an equality, then the variable $y_i$ is unrestricted.
### 3.2.2 Dual Objective Function
If (P) is a minimization problem, then (D) is a maximization problem and vice versa. The objective function coefficient for the variable $y_i$ in the dual problem equals the right-hand side constant $b_i$ of the $i$th constraint of (P).
### 3.2.3 Constraints of the Dual Problem
If $A$ is the constraint matrix of (P), then $A^T$ is the constraint matrix of (D). The $j$th right-hand side constant of (D) equals the $j$th coefficient $c_j$ in the objective function of (P).

If the $j$th variable of (P) is non-negative, then the $j$th constraint of (D) is an inequality of canonical form. If the $j$th variable of (P) is non-positive, then the $j$th constraint of (D) is an inequality of non-canonical form. Finally, if the $j$th variable of (P) is unrestricted, then the $j$th constraint of (D) is an equality.
### 3.2.4 Summary
The above rules can be summarized as follows:
$$
\begin{array}{rl}
\textbf{primal/dual constraint} & & \textbf{dual/primal variable} \\
\text{canonical inequality} & \Longleftrightarrow & \ge 0 \\
\text{non-canonical inequality} & \Longleftrightarrow & \le 0 \\
\text{equality} & \Longleftrightarrow & \text{unrestricted}
\end{array}
$$

![[k10_constructing_the_dual_problem.png]]

The number of variables in the primal problem becomes the number of constraints in the dual problem and vice versa.

[[Primal to Dual Conversion Example#Example from lecturer|Example]]
# 4 Strong and Weak Duality
## 4.1 Weak Duality
The primal objective is always equal or bigger than the dual objective.

Any feasible point for the dual is a lower bound on the optimal solution to the primal, and vice versa. 

For any feasible solution $x$ to the primal, and any feasible solution $y$ to the dual:
Primal value $z \le w$ Dual value

This means the value of the objective function in the maximization primal is always less than or equal to the minimization dual.

Weak duality is always true, as it applies to any feasible solution even if not optimal
## 4.2 Strong Duality
If both the primal and dual problems have feasible solutions and are bounded, then:
Optimal primal value $z^* = w^*$ Optimal dual value

This is only true for optimal solutions. Requires that both problems be feasible and bounded.