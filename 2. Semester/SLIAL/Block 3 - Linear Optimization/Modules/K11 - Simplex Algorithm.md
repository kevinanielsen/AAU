**Literature:** AEP: Section 8.2.2 up to Theorem 8.7 (you do not have to read the proof)+Chapter 9.

> If there exists an optimal solution then there exists an optimal solution among the basic feasible solutions

A basic solution that also satisfies the non-negativity constraints is called a basic feasible solution (BFS).

**Equivalence between extreme point and BFS**
Suppose $A \in \mathbb{R}^{m \times n}$ with rank $A = m$, and $b \in \mathbb{R}^m$. Then, a vector $x \in \mathbb{R}^n$ is an extreme point of the set $\{x \in \mathbb{R}^n \vert Ax=b; x \ge 0^n \} \ne \emptyset$ if and only if it is a basic feasible solution.
# The Algorithm
Assume we have a linear program in standard form:
$$
\begin{array}{lrrl}
\text{minimize} &z=c^Tx \\
\text{subject to} \\
&Ax=b, \\
&x\ge 0^n,
\end{array}
$$
where $A \in \mathbb{R}^{m\times n}, n > m$, rank $A=m, b \ge 0^m$, and $c \in \mathbb{R}^n$. 

At each iteration the simplex algorithm starts at the current BFS and moves to an adjacent BFS such that the objective function value decreases. It terminates with an optimal BFS (if there exists a finite optimal solution), or a direction of unboundedness.

