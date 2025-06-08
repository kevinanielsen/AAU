**Literature:** Rosen, Sections 7.1-7.2.6
# 1 Discrete Probability
## 1.1 Finite Probability
An **experiment** is a procedure that yields one of a given set of possible outcomes.
The **sample space** of the experiment is the set of possible outcomes.
An **event** is a subset of the sample space.

Laplace's definition of the probability of an event with finitely many possible outcomes is stated as
> If $S$ is a finite nonempty sample space of equally likely outcomes, and $E$ is an event, that is, a subset of $S$, then the probability of $E$ is $p(E)=\frac{\vert E \vert}{\vert S \vert}$.

According to this definition, the probability of an event is between 0 and 1.
## 1.2 Probabilities of Complements and Unions of Events
We can use counting techniques to find the probability of events derived from other events.
> Let $E$ be an event in a sample space $S$. The probability of the event $\bar E = S - E$, the complementary event of $E$, is given by $$p(\bar E)=1-p(E).$$

The probability of the union of two events can be computed with the following formula:
$$p(E_1 \cup E_2)=p(E_1)+p(E_2)-p(E_1 \cap E_2).$$
# 2 Probability Theory
## 2.1 Assigning Probabilities
Let $S$ be the sample space of an experiment with a finite or countable number of outcomes. We assign a probability $p(s)$ to each outcome $s$. We require that two conditions be met:
$$
(i) \quad 0 \le p(s) \le 1 \; \text{for each } s \in S
$$
and
$$
(ii) \quad \sum_{s \in S}p(s)=1.
$$
In words, the probability of each outcome must be a nonnegative real number no greater than 1, and the sum of the probabilities of the outcomes must add up to 1. 

If there are $n$ possible outcomes $x_1, x_2, \dots, x_n$, the two conditions to be met are
$$
\begin{aligned}
(i)&\quad 0 \le p(x_i) \le 1 \text{ for } i =1,2,\dots,n \\
(ii)&\quad \sum_{i=1}^n p(x_i)=1.
\end{aligned}
$$
The function $p$ from the set of all outcomes of the sample space $S$ is called a probability distribution.

> Suppose that $S$ is a set with $n$ elements. The uniform distribution assigns the probability $1/n$ to each element of $S$

## 2.2 Probabilities of Complements and Unions of Events
If $E_1, E_2, \dots$ is a sequence of pairwise disjoint events in a sample space $S$, then
$$
p \left( \bigcup_i E_i \right)=\sum_i p(E_i).
$$
## 2.3 Conditional Probability
Suppose a coin is flipped three times, and all eight possibilities are equally likely. Suppose we know that the event $F$, that the first flip comes up tails, occurs. Given this information, what is the probability of the event $E$, that an odd number of tails appears? Because the first flip comes up tails, there are only four possible outcomes: 
$$TTT, TTH, THT, THH.$$
An odd number of tails appears only for the outcomes $TTT$ and $THH$. Because the eight outcomes have equal probability, each of the four possible outcomes, given that $F$ occurs, should also have an equal probability of $1/4$. This suggests that the probability of $E$ is $2/4=1/2$ given that $F$ occurs. 

This is called the conditional probability of $E$ given $F$. 

> Let $E$ and $F$ be events with $p(F) > 0$. The conditional probability of $E$ given $F$, denoted by $p(E \vert F)$, is defined as 
> $$p(E|F)=\frac{p(E \cap F)}{p(F)}.$$
## 2.4 Independence
Suppose a coin is flipped three times. Does knowing that the first flip comes up tails (event $F$) alter the probability that tails comes up an odd number of times (event $E$)? I.e., is it the case that $p(E|F)=p(E)$? This equality is valid for the events _E_ and _F_, because $p(E|F)= 1/2$ and $p(E)= 1/2$. Because the equality holds, we say that $E$ and $F$ are independent events.
> The events $E$ and $F$ are independent if and only if $p(E \cap F)=p(E)p(F)$. 

### 2.4.1 Pairwise and Mutual Independence
> The events $E_1, E_2, \dots, E_n$ are pairwise independent if and only if $p(E_i \cap E_j)=p(E_i)p(E_j)$ for all pairs of integers $i$ and $j$ with $1\le i \le j \le n$. These events are mutually independent if $P(E_{i_1} \cap E_{i_2} \cap \cdots \cap E_{i_m})=p(E_{i_1})p(E_{i_2}) \cdots p(E_{i_m})$ whenever $i_j, j =1,2,\dots,m$, are integers with $\le i_1 < i_2<\cdots<i_m \le n$ and $m \ge 2$. 

## 2.5 Bernoulli Trials and the Binomial Distribution
Suppose that an experiment can have only two possible outcomes. For instance, when a bit is generated at random, the possible outcomes are 0 and 1. Each performance of an experiment like this is called a Bernoulli trial. A possible outcome is called a success or a failure. If $p$ is the probability of success and $q$ is the probability of a failure, it follows that $p+q=1$. 

> The probability of exactly $k$ successes in $n$ independent Bernoulli trials, with probability of success $p$ and probability of failure $q=1-p$, is
> $$C(n,k)p^kq^{n-k}.$$

We denote by $b(k;n,p)$ the probability of $k$ successes in $n$ independent Bernoulli trials with probability of success $p$. Considered as a function of $k$, we call this function the binomial distribution.