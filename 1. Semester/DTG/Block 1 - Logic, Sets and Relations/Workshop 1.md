# Exercise 1
1. **Write down the relation S given in figure 1 as a set.**
$$S = \{(Mia, Mia), (Bob, Bob), (Liv, Liv), (Noa, Noa), (Gus, Gus), (Ida, Ida), (Tom, Tom), (Bob, Mia), (Bob, Liv), (Liv, Tom), (Liv, Noa), (Noa, Tom), (Gus, Liv), (Gus, Tom), (Ida, Gus)\}$$
2. **What is the cardinality of the relation?**
The cardinality of this relation can be found by counting the number of relations in $S$ or by counting the number of arrows in figure 1. 

The cardinality of the relation is therefore 15.

3. **The relation can be described as a subset of a cartesian product. Which cartesian product does this refer to here and what is its cardinality?**
The relation could be the subset of a cartesian product of set $A$. E.g. $A \bigtimes A$, which since $\left| A \right| = 7$, then the cardinality of this cartesian product would be $7 * 7 = 49$. 

4. **Decide whether the relation above is reflexive, symmetric, transitive, or antisymmetric. Explain why it has or does not have these properties.** 
   **Consider what it means for a social network to have these properties.**
Since every element in the set $A$ has a relation to itself, in other words, for every $a \in A$ there exits $(a, a) \in S$, the relation is said to be reflexive. 

The relation is not symmetric as that would mean for every outgoing relation, there would have to be one coming back e.g. for all $(a,b) \in S$, it holds that $(b,a) \in S$. 

The relation is, however, antisymmetric as for every relation $(a,b)$ and $(b,a)$ it holds that $a=b$. 

The relation is not transitive, as that would mean that for every relation $(a,b)$ and $(b,c)$ there would have to be a relation $(a,c)$ and as we can see with $(Bob, Liv)$ and $(Liv, Noa)$ there is no $(Bob, Noa)$, which means that the relation $S$ is not transitive.

For a social network, it would make sense that every user has a relation (follows) themselves, as they would be able to see their own posts.
# Exercise 2
1. Explain the two options in terms of relations. The second option is related to a closure operation, which one?
Option a) would result in the original relation $S$ staying the same and no closure operations would occur, since it only targets the immediate followers.

Option b) which generates a chain reaction would result in a transitive closure operation. 

2. Find this closure for the relation in figure 1. We will call this new relation $S^∗$.
$$S^* = S \cup \{(Bob, Noa), (Bob, Tom), (Ida, Liv), (Ida, Tom)\}$$
![[23195.png]]
# Exercise 3
1. Consider the following sets
$$ 
\begin{aligned}
F_{Tom} &= {a \in A \mid (a, Tom) \in S^*} \\

F_{Noa} &= {a \in A \mid (a, Noa) \in S^*}
\end{aligned}
$$
   What do these sets describe? Which elements are in the sets $F_{Tom}$, $F_{Noa}$ and $F_{Tom} \cap F_{Noa}$.
The set $F_{Tom}$ describes all the users who follow Tom e.g. has a relation to Tom. The set $F_{Noa}$ describes all users who follow Noa. Lastly, the set $F_{Tom} \cap F_{Noa}$ describes the users who follow both Tom and Noa.
$$ 
\begin{aligned}
F_{Tom} &= \{Ida, Gus, Tom, Noa, Liv, Bob\} \\
F_{Noa} &= \{Bob, Liv, Noa\} \\
F_{Tom} \cap F_{Noa} &= \{Noa, Liv, Bob\}
\end{aligned}
$$

2. Let $B \subseteq A$ and consider $G_{Tom} = \{b \in B \mid (b,Tom) \in S^*\}$. Show that $G_{Tom} \subseteq F_{Tom}$.
Since $B \subseteq A$ e.g. all elements of $B$ must be in $A$, and $F_{Tom}$ is a "filtered" version $A$, then $G_{Tom}$ must be a "filtered" version of $B$. E.g. All elements of $G_{Tom}$ must be in $F_{Tom}$, therefore $G_{Tom} \subseteq F_{Tom}$. 
# Exercise 4
1. Consider the relation $R$ on $A = \{w, x, y, z\}$ given by
$$R = \{(w, w), (w, x), (x, y), (z, y)\}$$
![[Pasted image 20241229131520.png]]

| ==$R$== | w   | x   | y   | z   |
| ------- | --- | --- | --- | --- |
| w       | 1   | 1   | 0   | 0   |
| x       | 0   | 0   | 1   | 0   |
| y       | 0   | 0   | 0   | 0   |
| z       | 0   | 0   | 1   | 0   |
2. Find the reflexive closure $\tilde{R}$ of $R$.
$\tilde{R}=R \cup \{(x,x), (y,y), (z,z)\}$
![[74327.png]]

| ==$\tilde{R}$== | w   | x   | y   | z   |
| --------------- | --- | --- | --- | --- |
| w               | 1   | 1   | 0   | 0   |
| x               | 0   | 1   | 1   | 0   |
| y               | 0   | 0   | 1   | 0   |
| z               | 0   | 0   | 1   | 1   |

3.  **We will now continue with constructing succesive closures of this relation, but consider two diﬀerent orders.**
**a) Construct the symmetric closure $S$ of the reflexive closure $\tilde{R}$ of $R$. You may use whichever representation of the relation you prefer.**
$$S = \tilde{R} \cup \{(x,w), (y,x), (y,z)\}$$
![[93924.png]]

| ==$S$== | w   | x   | y   | z   |
| ------- | --- | --- | --- | --- |
| w       | 1   | 1   | 0   | 0   |
| x       | 1   | 1   | 1   | 0   |
| y       | 0   | 1   | 1   | 1   |
| z       | 0   | 0   | 1   | 1   |

**b) Construct the transitive closure $S^*$ of $S$.**
$$S^* = S \cup \{(w,y), (y,w), (x,z), (z,x)\}$$
![[76395.png]]

| ==$S^*$== | w   | x   | y   | z   |
| --------- | --- | --- | --- | --- |
| w         | 1   | 1   | 1   | 0   |
| x         | 1   | 1   | 1   | 1   |
| y         | 1   | 1   | 1   | 1   |
| z         | 0   | 1   | 1   | 1   |

**a) Now begin by constructing the transitive closure $T$ of the reflexive closure$\tilde{R}$. You may use whichever representation of the relation you prefer.**
$$T = \tilde{R} \cup \{(w,y)\}$$
![[99004.png]]

| ==$T$== | w   | x   | y   | z   |
| ------- | --- | --- | --- | --- |
| w       | 1   | 1   | 1   | 0   |
| x       | 0   | 1   | 1   | 0   |
| y       | 0   | 0   | 1   | 0   |
| z       | 0   | 0   | 1   | 1   |

**b) Next construct the symmetric closure $T'$ of $T$.**
$$T' = T \cup \{(x,w), (y,x), (y,z), (y,w)\}$$
![[89554.png]]

| ==$T'$== | w   | x   | y   | z   |
| -------- | --- | --- | --- | --- |
| w        | 1   | 1   | 1   | 0   |
| x        | 1   | 1   | 1   | 0   |
| y        | 1   | 1   | 1   | 1   |
| z        | 0   | 0   | 1   | 1   |
5. **Compare the results from the two previous tasks. Which of the two final relations $S^*$ and $T'$ is an equivalence relation?**
$T'$ Is not an equivalence relation since it is missing the transitive property as seen by there not being the following relations $(z,x), (x,z)$. It is, however, both symmetric and reflexive. 

$S^*$ Is not an equivalence relation either since there is missing the relations $(w,z), (z,w)$ which would make it transitive. Like the $T'$ relation, it is only symmetric and reflexive.