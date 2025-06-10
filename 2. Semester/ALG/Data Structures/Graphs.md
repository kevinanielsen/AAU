- A way of storing objects and their internal relations.
- Nodes/vertices connected by edges
- We specify a graph $G=(V,E)$, where $V$ is the amount of nodes and $E \subset V \times V$ is the amount of edges.
- Can be used for:
	- Dependency trees
	- Timeseries
	- Pathfinding
	- Social networks, the internet can be thought of as graphs.

- Come in two variants:
	- Directed Graphs
		- Every edge has a direction.
		- An edge $(u,v)\in E$ goes from node $u$ to node $v$.
	- Undirected Graphs
		- Has edges $(u,v)\in E$ that are not directions but connections that go both ways between $u$ and $v$.
- When analyzing graphs, we define the complexity to be a function of both $|V|$ and $|E|$.
- In a graph with $(|E|)$ edges there can be a maximum of 
	- $|E| = \left(\frac{|V|}{2}\right)=\frac{|V|(|V|-1)}{2}=O(|V|^2)$ nodes in an undirected graph, and
	- $|E|=|V|(|V|-1)=O(|V|^2)$ nodes in a directed graph.
- If $|E|$ is much less than $|V|^2$ we say that the graph is sparse.
- If $|E|$ is close to $|V|^2$ we say that the graph is dense.
- Weighted graphs also exist. Here, we assume a weight function $w:E \to \mathbb{R}$, where $w(u,v)$ defines the weight of the edge from $u$ to $v$.

# 1 Representations of Graphs
## 1.1 Adjacency Matrices
We can represent a graph as an adjacency matrix of size $|V|^2$, where
- Every element in the matrix $A=(a_{ij})$ defines that $$a_{ij}=\begin{cases}1& \text{if }(i,j)\in E \\ 0& \text{otherwise.} \end{cases}$$
- When looking at weighted graphs, we let $a_{ij}=w(i,j)$ if $(i,j)\in E$.
- $O(|V|^2)$ space complexity.
	- Best if the graph is dense.
## 1.2 Adjacency Lists
Another way of representing graphs is using adjacency lists. 
- An adjacency list for a graph $G=(V,E)$ consists of an array or hash table $Adj[1:|V|]$.
- For every node $u \in V$, we have a list $Adj[u]$, which contains all nodes $v$ where $\{u,v\}\in E$.
- $O(|V|+|E|)$ space complexity.
	- This is better if the graph is sparse.
# 2 Searching in Graphs
## 2.1 Breadth-First Search
- BFS searches the breadth first
- Given a graph $G=(V,E)$ and a start node $s\in V$, BFS finds the shortest path from $s$ to all other nodes in $G$ which we can get to from $s$. (This only works for non-weighted graphs).
- It visits all nodes in $V$ which can be reached from $s$, and at every node $v$, it notes its predecessor $v.\pi=u$.
- As an artifact, we get a predecessor subgraph of $G$ in the shape of $G_\pi=(V_\pi, E_\pi)$.
	- Where $$ \begin{aligned} V_\pi&=\{v\in V : v.\pi \ne \text{NIL}\}\cup \{s\} \\ V_\pi&=\{(v.\pi,v):v \in V_\pi - \{s\}\} \end{aligned} $$
	- This subgraph is called a breadth-first tree $T$ with root in $s$ and where all paths from $s$ to another node $v \in T$ corresponds to the shortest path from $s$ to $v$ in $G$.
- It works both on directed and undirected graphs.

It works by:
- Starting from $s$ and assumes that every other node is infinitely far away from $s$.
- It saves all neighbors of $s$ in a queue $Q$ and notes how far away they were.
- It dequeues the first element in $Q$ and adds its neighbors to $Q$ and notes its distance to $s$.
- This pattern is continued until all nodes have been visited.

[[bfs_pseudo.png|BFS Pseudo Code]]

- All nodes get the following attributes
	- `u.color` $\in \{\text{WHITE,GRAY,BLACK}\}$.
	- `u.d`, the distance from `s`.
	- `u.π`, `u`'s parent in the breadth-first tree.
- We set `s` to be gray and note its distance (to itself) to be 0 and insert it as the first and only element in `Q`.
- While `Q` is not empty, we dequeue the first element `u`.
- From here, we check each of `u`'s neighbors and if they are WHITE, we have not processed them yet.
- In that case, we set them to GRAY, set the distance, set their parent to `u` and add them to `Q`.
- Lastly, we set them to BLACK.

The complete runtime complexity is $O(|V|+|E|)$.
## 2.2 Depth-First Search
- Does not start with a certain start-node, instead it moves through all nodes of the graph.
- Instead of exploring levels of the graph, it follows the trail from a node to the 'deepest' descendant before moving on to its neighbors.
- With DFS we get a 'depth-first forest' instead of a 'breadth-first tree'. Here, there can be multiple roots that are not connected.
	- A predecessor subgraph $G_\pi = (V, E_\pi)$ where $$E_\pi=\{(v.\pi,v): v \in V \text{ and } v.\pi \ne \text{NIL}\}$$
[[dfs_pseudo.png|Depth-First Search Pseudo Code]]

- It initializes all nodes and starts the "timer"
- Then, it takes all nodes one at a time and calls the sub-procedure `DFS-Visit` on each of them (if they are still white). 
- In `DFS-Visit`, it notes when we 'explored' `u` by setting `u.d = time`.
- Next, it takes all neighbors `v` to `u`, and sets `v.π`, and calls `DFS-Visit` recursively on `v` (if it is white).
- Lastly, it notes when it completed `u` by setting `u.f = time`, and sets the color to black.

DFS has a total runtime complexity of $O(|V|+|E|)$. 
# 3 Sorting
## 3.1 Topological Sorting
- An algorithm used for sorting nodes in a directed acyclic graph (DAG).
- The order says that if there exists an edge from `u` to `v` in `G`, then `u` needs to come before `v` in the output-list.
- This can for example be used when compiling software that uses sub-modules which might be dependent on each other.

[[topological_sort_pseudo.png|Topological-Sort Pseudo Code]]

It has a runtime complexity of $O(|V| + |E|)$. 