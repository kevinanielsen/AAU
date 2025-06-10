## 0.1 Versions of the problem
There are a a couple of different versions of the shortest-paths problem:
- **Single-source shortest path**: Find the shortest way from a single given start-node `s` to all other nodes in a graph.
- **Single-destination shortest-paths**: Find the shortest way from all nodes to a single end-node `t`.
	- If we turn all edges in the graph around, this is reduced to the single-source problem.
- **Single-pair shortest-path**: Find the shortest path between just two nodes, `u`and `v`.
	- This is automatically solved by a single-source solution. There are no known algorithms for solving this faster than the single-source problem.
- **All-pairs shortest-paths**: Find the shortest path between all possible pairs of nodes `u` and `v`. 
	- Gets solved by solving the single-source problem from all nodes in a graph.
## 0.2 Weights, Paths and Shortest Path
- In a weighted graph, all edges $(u,v)\in E$ are associated with a weight given by $w(u,v)$, where $w:E \to \mathbb{R}$. 
- The weight $w(p)$ of a path $p=\langle v_0, v_1, \cdots, v_k \rangle$ is the sum of weights of the edges on the path: $$w(p)=\sum_{i=0}^{k-1}w(v_i,v_{i+1})$$
- We let $\delta (u,v)$ be the weight of the shortest path between $u$ and $v$ be defined by: $$\delta(u,v)=\begin{cases} \min\{w(p):u \stackrel{p}{\rightsquigarrow} v\}  \\ \infty \end{cases}$$
## 0.3 Loops in Graphs
A loop in a graph is a path, that goes from a node $u$ and ends (via 0 or more intermediate nodes) back at $u$ again.
- If a graph $G=(V,E)$ contains a loop with negative weight, which can be reached from node $s$, then $\delta(s,v)$ is not well-defined.
- For a negative loop, we can go around another time and find a path with a smaller total weight.
- We define $\delta (s,v)=-\infty$, if there exists a negative loop on the path between $s$ and $v$.
- If there exists a loop with a positive weight, it will never be part of the shortest path.
	- We will always be able to remove the loop (which goes from $u$ to $u$) and thereby get a shorter path.
- If we have a path with weight 0, it can be removed without changing $\delta(u,v)$. We can therefore assume that shortest paths do not include any loops.
## 0.4 Optimal Structure
The shortest path between too nodes also contains the shortest path between the other nodes on the path. If $p = \langle v_0, v_1, \dots, v_k\rangle$ is a shortest path between nodes $v_0$ and $v_k$, then for all $i$ and $j$ where $0\le i \le j \le k$ the path $p_{ij}=\langle v_i, v_{i+1}, \dots, v_j\rangle$ is the shortest path between $v_i$ and $v_j$. 
This property is used by Dijkstra's Algorithm.
## 0.5 Representation of Shortest Paths
With the same technique as [[Graphs#2.1 Breadth-First Search|BFS]], we save a node's predecessor in the attribute $\pi$, which gives us a predecessor subgraph $G_\pi=(V_\pi, E_\pi)$ given by:
$$
\begin{aligned}
V_\pi &= \{v \in V:v.\pi \ne \text{NIL}\} \cup \{s\}, \\
E_\pi &=\{ (v.\pi, v) \in E : v \in V_\pi - \{s\} \}
\end{aligned}
$$
- When the algorithm terminates, $G_\pi$ will be the shortest-path tree (but not necessarily during the run of the algorithm).
- We define a shortest-path tree with root in $s$ as a directed subgraph $G'=(V', E')$ where $V'\subseteq V$ and $E' \subseteq E$ so that
	1. $V'$ is all the nodes in $V$ that can be reached from $s$,
	2. $G'$ is a tree with root in $s$, and
	3. for all $v \in V'$ the simple path from $s$ to $v$ in $G'$ is the shortest path from $s$ to $v$ in $G$.
## 0.6 Relaxation
Relaxation is a fundamental technique used in all our graph algorithms. It is a way of potentially lowering the estimate of the distance from $s$ to $v$.
- Every node `v` has an attribute `v.d` that defines the weight on the shortest known path from `s` to `v`.
- When we relax an edge from `u` to `v`, we check if arriving at `v` from `u` is shorter than where ever we came from.
- We check if `v.d` (our earlier estimate) is bigger than `u.d` (the distance from `s` to `u`) plus `w(u,v)` (the weight of the edge between `u` and `v`).

[[relax_pseudo.png|Relax Pseudo Code]]
## 0.7 Initialization
- Given a graph $G=(V,E)$ and a start-node $s$, we se the shortest-paths estimate `v.d`for all nodes in `V` til $\infty$ and their predecessor `v.π` to NIL.
- Next we set `s.d = 0`.

[[initialize_single_source_pseudo.png|Initialize-Single-Source Pseudo Code]]
# 1 Shortest Paths in DAGs
- A Directed Acyclic Graph (DAG) is a directed graph with no loops.
- It utilizes relaxation to get the shortest paths. It works by sorting topologically and then relaxing the edges in that order.
	- It has a runtime complexity of $O(V+E)$.

[[dag_shortest_paths_pseudo.png|DAG-Shortest-Paths Pseudo Code]]
# 2 Bellman-Ford
An algorithm that solves the single-source shortest paths problem for all types of weighted graphs (including ones with negative weights).
- If a graph has negative loops, it identifies them and returns that no solutions exist.
- The algorithm finds the shortest paths from $s$ and their weights.
- The shortest path has a maximum of $|V|-1$ edges, so we can find the shortest paths by relaxing all edges $|V|-1$ times.
	- And if there still exists a shorter path (by relaxing again), it means that there exist a negative loop.

[[bellman_ford_pseudo.png|Bellman-Ford Pseudo Code]]

- It starts by initializing the problem
- Then it loops $|V|-1$ times and in every iteration, it calls relax on **all** edges.
- It then checks if the weights can be reduced further, if yes, then there is a negative loop and it returns FALSE, else, it returns TRUE.

The runtime complexity is $O(VE)$.
# 3 Dijkstra's Algorithm
It is not as general as Bellman-Ford, but it has a better runtime with the right implementation.
- The algorithm requires that there are no negative edges (and thereby no negative loops)
- Implementation looks like BFS but it uses a priority queue where `v.d` is the key, instead of a regular FIFO-queue.

[[dijkstra_pseudo.png|Dijkstra Pseudo Code]]

1. We initialize the problem
2. Create a min-priority queue `Q`
3. Insert all nodes in `Q`
4. While `Q` is not empty, we remove the least element and save it in `u`.
5. We relax all neighbors of `u` and update the queue if we lowered the shortest-path estimate `v.d`.
6. When the queue is empty, we are done.

If `Q` is implemented as a simple list, we have a runtime complexity of $O(V^2)$, if we use a binary heap and make a min-priority queue instead however, we get a runtime complexity of $O((E+V) \log V)$. It can be further enhanced by using a Fibonacci heap, which gets us a runtime of $O(E+V\log V)$.