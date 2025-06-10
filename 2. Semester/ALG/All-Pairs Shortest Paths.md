> Given a weighted directed graph $G=(V,E)$ with a weight function $w: E\to \mathbb{R}$, we want to find the shortest path between $i$ and $j$ for all pairs of nodes $i,j\in V$.

This problem can be solved easily by running Bellman-Ford or Dijkstra $V$ times:
- With Dijkstra this gives a runtime of $O(VE+V^2 \log V)$.
	- For a dense graph, we have $E \approx V^2$, which gives $O(V^3)$, plus the $V^2\log V$.
- For Bellman-Ford, we would have a runtime of $O(V^2E)$.
	- Once again, for a dense graph this would mean $O(V^4)$.

- If we assume that all nodes in $V$ are numbered so $V=\{1,2,3,\dots,n\}$.
- We allow negative weights on edges.
- We assume that $G$ does not contain any negative loops.
- Our adjacency matrix has the shape $W=(w_{ij})$ and for each pair of nodes $(i,j)\in V \times V$, we have 
$$
w_{ij}=\begin{cases} 0 & \text{if }i=j \\ w(i,j) &\text{if }i\ne j \text{ and } (i,j)\in E \\ \infty &\text{if } i\ne j \text{ and }(i,j)\notin E\end{cases}
$$
- The final output is a $|V| \times |V|$ matrix $D=(d_{ij})$, where for each $i,j\in V$ we have $d_{ij}=\delta(i,j)$.
# Floyd-Warshall
Floyd-Warshall is a dynamic programming algorithm, that characterizes the structure of the optimal solution in the following way:
- First, we define an intermediate node on a simple path $p = \langle v_1, v_2, \dots, v_n \rangle$ to be any node in $p$ except $v_1$ and $v_n$.
- Imagine all paths from $i$ to $j$, where the intermediate nodes come from the set $\{ 1,2,\dots,k \}$ and let $p$ be the shortest path. If the node $k$ is not an intermediate node in $p$, then all intermediate nodes in $p$ belong to the set $\{1,2,\dots,k-1\}$.
- If the node $k$ is an intermediate node in $p$, we can split $p$ into two: $i \stackrel{p_1}{\rightsquigarrow}k \stackrel{p_2}{\rightsquigarrow}j$, i.e., the shortest path from $i$ to $k$ and the shortest path from $k$ to $j$.

So the optimal solution can be defined recursively:
- First, let $D^{(k)}=\left(d_{ij}^{(k)}\right)$ be a $|V|\times|V|$ matrix, and let $d_{ij}^{(k)}$ denote the weight of the shortest path from node $i$ to node $j$, where all intermediate nodes come from the set $\{1,2,\dots,k\}$.
- If $k=0$, the set is empty (i.e., there are no intermediate nodes on the path).
	- Thereby, $d_{ij}^{(0)}$ determines the weight of the shortest path from $i$ to $j$ that consists of 0 (no path) or 1 edge. In other words, $d_{ij}^{(0)}=w_{ij}$.
- If $k \ge 1$, then the shortest path from $i$ to $j$ is either
	- The path that only needs to visit nodes from the set $\{1,2,\dots,k-1\}$, i.e., $d_{ij}^{(k-1)}$ or 
	- the path we get by first going from $i$ to $k$ (via nodes in $\{1,2,\dots,k-1\}$) and then from $k$ to $j$, i.e., $d_{ik}^{(k-1)}+d_{kj}^{(k-1)}$.
- This means that we can define $d_{ij}^{(k)}$ recursively
$$
d_{ij}^{(k)}=\begin{cases}
w_{ij} & \text{if }k=0,\\
\min \{d_{ij}^{(k-1)},d_{ik}^{(k-1)}+d_{kj}^{(k-1)} \} & \text{if } k\gt 0
\end{cases}
$$

[[floyd_warshall_pseudo.png|Floyd-Warshall Pseudo Code]]

- The input is our adjacency matrix $W$, that represents our graph
- We set $D^{(0)}=W$, because $d_{ij}^{(0)}=w_{ij}$ for all $i,j\in V$.
- Next, we iterate over all $n$ nodes
	- Inside the loop, we create $D^{(k)}$, that we will manipulate.
- Then we iterate over all pairs of nodes $(i,j)$
	- Now, we can set $d_{ij}^{(k)}$ to the lesser of $d_{ij}^{(k-1)}$ and $d_{ik}^{(k-1)}+d_{kj}^{(k-1)}$.
- Lastly, we return $D^{(n)}$ as per definition contains the weights of all the shortest paths.

The runtime complexity is $\Theta(n^3)$ and thereby faster than [[Single-Source Shortest Path#2 Bellman-Ford|Bellman-Ford]] when $E=\Omega(V)$.

From the returned adjacency matrix, we now need to find the shortest paths from this.
- We construct a predecessor matrix $\Pi = (\pi_{ij})$, where $\pi_{ij}$ is the predecessor to node $j$ on the shortest path $i$.
- $\Pi$ can either be made directly from $O(n^3)$ time
- Or it can be built during the Floyd-Warshall following the same principles as $D$, where we start with $\Pi^{(0)}$, then $\Pi^{(1)}$ etc.
	- We start with
$$
\pi_{ij}^{(0)} = \begin{cases}
\text{NIL} & \text{if }i=j \text{ or } w_{ij}=\infty, \\
i & \text{if } i \ne j \text{ or } w_{ij} \lt \infty.
\end{cases}
$$
	- Once again, if $k$ is an intermediate node on the path from $i$ to $j$, then we can simply look at the path from $k$ to $j$:
$$
\pi_{ij}^{(k)} = \begin{cases}
\pi_{kj}^{(k-1)} & \text{if } d_{ij}^{(k-1)} > d_{ik}^{(k-1)} + d_{kj}^{(k-1)} \text{ (}k\text{ is an intermediate vertex)} \\
\pi_{ij}^{(k-1)} & \text{if } d_{ij}^{(k-1)} \leq d_{ik}^{(k-1)} + d_{kj}^{(k-1)} \text{ (}k\text{ is not an intermediate vertex)}
\end{cases}
$$
