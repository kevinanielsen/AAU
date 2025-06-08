**Literature:** [Lay], Section 4.9 + slides. Skim through [VMLS], Chapter 9 for some examples/applications
# 1 Markov Chains
**Example**
An example of a markov chain could be a web crawler. When changing websites, the surfer clicks on one of the outgoing links at random, independently from their previous browsing history. The independence is important and is called the markov property.

There are $n$ websites in total, indexed by numbers $1, \dots, n$. The set of states is thus $\{1,2, \dots, n\}$.
Assume that there is at least one link going "out" of each website. We construct a $n \times n$ matrix $A=[a_{ij}]$, where
$$
a_{ij} = \begin{cases} 
\frac1k &\text{if there is a link from j to i and there are k links in total from j} \\
0 &\text{otherwise}
\end{cases}
$$
Then $A$ is a stochastic matrix.
![[k15_web_surfer_example.png]]
With the graph above, we have the following matrix, where the first column corresponds to website, $A$, and the rows being what the probability is of moving to that site.
$$
A= \begin{bmatrix*}[r]
0 & \frac12 & 0 & \frac12 & 1 \\
1 & 0 & 0 & 0 & 0 \\
0 & \frac12 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & \frac12 & 0
\end{bmatrix*}
$$
E.g., from A, there is a 100% probability of moving to B.

If we begin with $p^{(0)} = \begin{bmatrix*}[r] \frac15 \\ \frac15 \\ \frac15 \\ \frac15 \\ \frac15 \end{bmatrix*}$, then
$$
p^{(10)}=A^{10}p^{(0)} = \begin{bmatrix*}[r]
0.306 \\ 0.306 \\ 0.150 \\ 0.163 \\ 0.075
\end{bmatrix*}
$$
This is because
$$
\begin{aligned}
p^{(1)}&=Ap^{(0)} \\
p^{(2)}&=Ap^{(1)} =AAp^{(0)} =A^2p^{(0)}
\end{aligned}
$$

## 1.1 Discrete Random Systems
- A system has a finite number $n$ of possible states (denoted $a_1, a_2, a_3, a_4$)
- The system's state is observed only at discrete time intervals (denoted $t_0, t_1, t_2, t_3$)
- The discrete time intervals will be indexed by numbers 0, 1, 2, 3,...
- The system's state at times 0,1,2,3,... is described by a state vector or a probability vector $x_0, x_1, x_2, x_3, \dots$
$$p(\text{the system has the state } a_j \text{ at the time } t_i) = (x_i)_j$$
Remember: $(x_i)_j \ge 0, \sum_{j=1}^n (x_i)_j=1$. (Probability cannot be negative)

## 1.2 Markov Chains
A Markov chain is a random system satisfying the property
$$x_{i+1}=Px_i,$$
where $P$ is a $n \times n$ matrix. In words, the next state of the system can be determined by multiplying the previous state by some matrix $P$. 

The entries, $P_{jk}$ can be defined as
$$
P_{jk}=p(\text{state at time }i+1 \text{ is }a_j \quad| \quad \text{state at time } i \text{ is } a_k)
$$
I.e., the probability that the state at the next time $i+1$ is $a_j$, given that the state at the current time $i$ is $a_k$.
## 1.3 Example
- Xkøbing is a town, consisting of a downtown and a suburb with a total population of 100.000.
- Each year 5% of the population of the suburb moves downtown and 3% of the population of the downtown move to the suburbs.
- After $t$ years the population of the suburb is $x_t^f$ and that of the downtown is $x_t^m$.
- The corresponding probability vector is $$x_t=(x_t^f/100\,000, x_t^m/100\,000).$$
- Let $P = \begin{bmatrix*}[r] 0.95 & 0.03 \\ 0.05 & 0.97 \end{bmatrix*}$. Then $x_{t+1}=Px_t$. In words, the people in the suburb have a 95% probability of staying in the suburbs, but with probability 5%, they move to downtown. Likewise, the people of the downtown have a 3% probability of moving to the suburbs and a 97% probability of staying. This is a markov chain because it upholds that $x_{t+1})=Px_t$
## 1.4 Stochastic Matrix 
$P$ is a stochastic matrix, if
- $0 \le P_{jk} \le 1$
- All column of $P$ are probability vectors: $$\sum_{j=1}^n P_{jk}=\sum_{j=1}^n p(\text{state at time } i +1 \text{ is } a_j \quad | \quad \text{state at time } i \text{ is } a_k)=1$$
## 1.5 Markov Property
Directly from its definition, the Markov chain has the following property:
The conditional probability at each observed time, given the previous history of the system, only depends on the last observed state, i.e.,
$$
p(E_{j_{i+1}, i+1}|E_{j_i} \cap E_{j_{i-1},i-1} \cap \cdots \cap E_{j_0},0)=p(E_{j_{i+1}i+1}|E_{j_{i},i}),
$$
where $E_{j,i}=$ the system has the state $a_j$ at time $t_i$

In words: "Where we got to at time $t_i$ is independent from where we come from".
## 1.6 Example: Peter's t-shirts
Peter owns only white and black t-shirts. Each morning he decides which t-shirt to wear based on the following principles:
- If Peter wore a black t-shirt the day before, there is 60% probability that he will wear a black t-shirt today.
- If Peter wore a white t-shirt the day before, there is 45% probability that he will wear a white t-shirt today.
![[k15_peters_shirts.png]]
Let $p_t^b(p_t^w)$ be the probability, that Peter wears a black (white) t-shirt on day $t$. 
Let the first column in the matrix represent the transition probabilities for black and second column for white t-shirts. Then the corresponding stochastic matrix is given by
$$
\begin{bmatrix*}[r]
0.6 & 0.55 \\
0.4 & 0.45
\end{bmatrix*}
$$
and the probability that Peter wears a black/white t-shirt on day $t+1$ is
$$
\begin{bmatrix*}[r]
p_{t+1}^b \\
p_{t+1}^w
\end{bmatrix*} = \begin{bmatrix*}[r]
0.6 & 0.55 \\
0.4 & 0.45
\end{bmatrix*} \begin{bmatrix*}[r]
p_t^b \\
p_t^w
\end{bmatrix*}
$$
# 2 Stationary Distribution
## 2.1 Definition
A vector $\pi$ is a stationary distribution for a Markov chain with a stochastic matrix $P$, if 
- $\pi$ is a probability vector (in particular, $\pi \ne 0$) and
- $P \pi = \pi$
Note that if $P \pi = \pi$, then
$$
0=P \pi - \pi = (P - I_n)\pi = (P - 1I_n)\pi
$$
We can consider 1 an [[SS02 - Eigenvalues and Eigenvectors#1 Eigenvector|eigenvalue]] because $P \pi = \lambda \pi$ with $\lambda = 1$, where $\pi$ is the eigenvector.

> Let $P$ be a stochastic matrix. Then 1 is an eigenvalue of $P$.
## Examples
**Peter's T-shirts**
For the example with Peter's t-shirts, the stochastic matrix is
$$
A = \begin{bmatrix*}[r]
0.6 & 0.55 \\
0.4 & 0.45
\end{bmatrix*}
$$
Then
$$
A^T \begin{bmatrix*}[r]
1 \\ 1
\end{bmatrix*} = \begin{bmatrix*}[r]
0.6 & 0.4 \\ 0.55 & 0.45
\end{bmatrix*} \begin{bmatrix*}[r]
1 \\ 1
\end{bmatrix*} = \begin{bmatrix*}
0.6+0.4 \\ 0.55 + 0.45
\end{bmatrix*} = \begin{bmatrix*}[r]
1 \\ 1
\end{bmatrix*}
$$
Therefore, $\lambda = 1$ is an eigenvalue of $A^T$ and consequently also of $A$. 

If $\pi$ is a stationary distribution, then $\pi$ is a solution to the homogenous system of linear algebraic equations $(A-I_n)\overrightarrow x = \overrightarrow 0$.

In our example
$$
A - I_2 = \begin{bmatrix*}[r]
-0.4 & 0.55 \\
0.4 & -0.55
\end{bmatrix*} \sim \begin{bmatrix*}
-0.4 & 0.55 \\
0 & 0
\end{bmatrix*}
$$
whose space of solutions is
$$
\overrightarrow x = k \begin{bmatrix*}[r]
0.55 \\ 0.4
\end{bmatrix*}, \quad \text{for } k \in \mathbb{R}
$$
Since $\pi$ is a probability distribution, we need to select $k$ so that the entries of $\pi$ sum up to one. This is the case for $k=\frac{20}{19}$. Therefore
$$
\pi = \frac{20}{19} \begin{bmatrix*}[r]
11/20\\8/20
\end{bmatrix*}= \begin{bmatrix*}[r]
11/19 \\ 8/19
\end{bmatrix*}
$$
**Example 2**
The stochastic matrix for a system is $P = \begin{bmatrix*}[r] 0.2 & 0.4 \\ 0.8 & 0.6 \end{bmatrix*}$
What is the stationary distribution?

$$
P-I_2= \begin{bmatrix*}[r]
-0.8 & 0.4 \\
0.8 & -0.4
\end{bmatrix*} \sim \begin{bmatrix*}[r]
-0.8 & 0.4 \\
0 & 0
\end{bmatrix*}
$$
$$
\begin{aligned}
-0.8x_1+0.4x_2&=0 \\
0.8x_1&=0.4x_2 \\
\Rightarrow 2x_2&=x_2
\end{aligned}
$$
$$\overrightarrow x = k \begin{bmatrix*}[r]
1 \\ 2
\end{bmatrix*}, \quad \text{for } k \in \mathbb R$$
$$\pi = \frac13 \begin{bmatrix*}[r]
1 \\2
\end{bmatrix*}= \begin{bmatrix*}[r]
1/3 \\ 2/3
\end{bmatrix*}$$

## When do we Have a Unique Stationary Distribution
> Let $P$ be a stochastic matrix. Assume that either all entries in $P$ are positive, or there is a positive integer $k$ such that all entries in $P^k$ are positive (Such stochastic matrices are called regular.) Then there is a unique probability vector $\pi$ such that $P \pi = \pi$. 