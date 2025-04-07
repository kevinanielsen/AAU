[[Discrete Probability]] and the definition of probability being $p(E)=\dfrac{\vert E \vert}{\vert S \vert}$ relies on the fact that all outcomes are equally likely. However, many experiments have outcomes that are not equally likely. An example could be a coin that is biased so it comes up heads twice as often as tails.

# Conditional Probability
Suppose a fair coin is flipped four times, and the first time it comes up heads. Given this information, what is the probability that heads comes up three times? To answer this we use the concept of conditional probability.

Let $S$ be the sample space of an experiment with a finite or countable number of outcomes. We assign a probability $p(s)$ to each outcome $s$. We require that two conditions be met:
$$ 
\begin{align}
(i)\quad &0 \leq p(s)\leq 1 \text{ for each } s \in S \\\\
(ii) \quad & \sum_{s \in S} p(s)=1.
\end{align}
$$
I.e., the probability of any outcome must be between 0 and 1, and the sum of the probability of all outcomes must be 1.

For $n$ possible outcomes $x_1, x_2, \dots, x_n$, the two conditions to be met are
$$ 
\begin{align}
(i)\quad &0 \leq p(x_i)\leq 1 \text{ for } i=1,2,\dots,n \\\\
(ii) \quad & \sum_{i = n}^n p(x_i)=1.
\end{align}
$$
The function $p$ from the set of all outcomes of the sample space $S$ is called a *probability distribution*.
# Assigning Probabilities
To model an experiment, the probability $p(s)$ assigned to an outcome $s$ should equal the limit of the number of times $s$ occurs divided by the number of times the experiment is performed, because this number grows without bound.
## Example
For a fair coin, the probability that heads comes up when the coin is flipped equals the probability that tails comes up, so the outcomes are equally likely. Consequently, we assign the probability $1∕2$ to each of the two possible outcomes, that is, $p(H)=p(T)=1/2$. 

For the biased coin where heads comes up twice as often as tails we have
$$
p(H)=2p(T).
$$
Because
$$p(H)+p(T)=1,$$
it follows that
$$2p(T)+p(T)=3p(T)=1.$$
We conclude that $p(T)=1/3$ and $p(H)=2/3$. 


# Definitions
Suppose that $S$ is a set with $n$ elements. The *uniform distribution* assigns the probability $1/n$ to each element of $S$.

The *probability* of the event $E$ is the sum of the probabilities of the outcomes in $E$. That is,
$$p(E)=\sum_{s \in E}p(s).$$
