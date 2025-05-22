$$
\begin{bmatrix*}[r]
0 & -3 & -6 & 4 & 9 \\
-1 & -2 & -1 & 3 & 1 \\
-2 & -3 & 0 & 3 & -1 \\
1 & 4 & 5 & -9 & -7
\end{bmatrix*}
$$
First nonzero column: 1, pivot entry: $(1,1)$. We pick nonzero element 1 in this column to be a pivot. We bring it to the pivot position by exchanging rows 1 and 4:
$$
\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
-1 & -2 & -1 & 3 & 1 \\
-2 & -3 & 0 & 3 & -1 \\
0 & -3 & -6 & 4 & 9 \\
\end{bmatrix*}
$$
Now, we need to eliminate nonzero entry -1 at the position $(2,1)$. We can do this by multiplying row 1 by 1 and adding it to row 2:
$$
\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
-2 & -3 & 0 & 3 & -1 \\
0 & -3 & -6 & 4 & 9 \\
\end{bmatrix*}
$$
Now, we need to eliminate nonzero entry -2 at the position $(3,1)$. We can do this by multiplying row 1 by 2 and adding it to row 3:
$$
\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
0 & 5 & 10 & -15 & -15 \\
0 & -3 & -6 & 4 & 9 \\
\end{bmatrix*}
$$
All entries under pivot position are eliminated. We will now ignore row 1 and proceed with the algorithm.

First nonzero column: column 2. Pivot entry: $(2,2)$. We pick nonzero element 2 in this column to be a pivot; it is already in the pivot position. Now we need to eliminate nonzero entry 5 at the position $(3,2)$. We can do this by multiplying row 2 by $\frac{5}{2}$ and subtracting it from row 3:
$$
\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
0 & 0 & 0 & 0 & 0 \\
0 & -3 & -6 & 4 & 9 \\
\end{bmatrix*}
$$
Now we need to eliminate nonzero entry -3 at the position at the position at position $(4,2)$. We can do this by multiplying row 2 by $\frac{6}{4}=\frac{3}{2}$ and adding it to row 4:
$$\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & -5 & 0 \\
\end{bmatrix*}$$
All entries under pivot position are eliminated. We will now ignore rows 1 and 2 and proceed with the algorithm.

First nonzero column: column 4. Pivot entry: $(3,4)$. We pick (the only) nonzero element -5 in this column to be a pivot. We bring it to the pivot position by exchanging rows 3 and 4:
$$\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
0 & 0 & 0 & -5 & 0 \\
0 & 0 & 0 & 0 & 0 \\
\end{bmatrix*}$$
At this point, the matrix is in the row echelon form!

# 1 Final Result
$$\begin{bmatrix*}[r]
1 & 4 & 5 & -9 & -7 \\
0 & 2 & 4 & -6 & -6 \\
0 & 0 & 0 & -5 & 0 \\
0 & 0 & 0 & 0 & 0 \\
\end{bmatrix*}$$
Pivot positions: $(1,1), (2,2), (3,4)$.
Pivot columns: $1,2,4$
Pivot elements: $1,2,-5$.