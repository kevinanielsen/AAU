**Literature:** [Rosen] Sections 7.2.7, 7.4 + slides
# 1 Random Variables (Stochastic Variables)
> A random variable is a function from the sample space of an experiment to the set of real numbers. That is, a random variable assigns a real number to each possible outcome.

> [!NOTE] Remark
> A random variable is a function. It is not a variable and it is not random!

Suppose that a coin is flipped three times. Let $X(t)$ be the random variable that equals the number of heads that appear when $t$ is the outcome. Then $X(t)$ takes on the following values
$$
\begin{aligned}
X(HHH)&=3, \\
X(HHT)&=X(HTH)=X(THH)=2, \\
X(TTH)&=X(THT)=X(HTT)=1, \\
X(TTT) &= 0.
\end{aligned}
$$
The distribution of a random variable $X$ on a sample space $S$ is the set of pairs $(r,p(X=r))$ for all $r \in X(S)$, where $p(X=r)$ is the probability that $X$ takes the value $r$.  (The set of pairs in this distribution is determined by the probabilities $p(X=r)$ for $r \in X(S)$.)

Each of the 8 possible outcomes when a coin is flipped three times has probability $1/8$. So, the distribution of the random variable $X(t)$ is determined by the probabilities $P(X=3)=1/8, P(X=2)=3/8, P(X=1)=3/8$, and $P(X=0)=1/8$. The distribution of $X(t)$ is the set of pairs $(3, 1/8), (2,3/8), (1,3/8), (0,1/8)$.
# 2 Expected Values
The expected value of a random variable is the sum over all elements in a sample space of the product of the probability of the element and the value of the random variable at this element.

The expected value, also called the expectation or mean, of the random variable $X$ on the sample space $S$ is equal to
$$
E(X)=\sum_{s \in S}p(s)X(s).
$$
The deviation of $X$ at $s \in S$ is $X(s)-E(X)$, the difference between the value of $X$ and the mean of $X$.

**Example**
Let $X$ be the number that comes up when a fair die is rolled. What is the expected value of $X$. 
Solution: The random variable $X$ takes the values 1,2,3,4,5, or 6 each with probability $1/6$. It follows that
$$E(x)=\frac16 \cdot 1+\frac16 \cdot 2+\frac16 \cdot 3+\frac16 \cdot 4+\frac16 \cdot 5+\frac16 \cdot 6=\frac{21}{6}=\frac72.$$

When an experiment has relatively few outcomes, the expected value of a random variable can be calculated directly from its definition. When the number of outcomes is large, we can find the expected value of a random variable by grouping together all outcomes assigned the same value by the random variables.

## 2.1 Theorem 1
If $X$ is a random variable and $p(X=r)$ is the probability that $X=r$, so that $p(X=r)=\sum_{s \in S, X(s)=r}p(s)$, then 
$$
E(X)=\sum_{r \in X(S)}p(X=r)r.
$$
## 2.2 Theorem 2
The expected number of successes when $n$ mutually independent [[K13 - Introduction to Probability Theory#Bernoulli Trials and the Binomial Distribution|Bernoulli trials]] are performed, where $p$ is the probability of success on each trial, is $np$. 

# 3 Linearity of Expectations
## 3.1 Theorem 3
if $X_i, i=1,2,\dots,n$ with $n$ a positive integer, are random variables on $S$, and if $a$ and $b$ are real numbers, then
$$
\begin{aligned}
(i)\quad& E(X_1+X_2+\cdots+X_n)=E(X_1)+E(X_2)+\cdots + E(X_n) \\
(ii)\quad& E(aX+b)=aE(X)+b.
\end{aligned}
$$
E.g., the expected value of the sum of random variables is the sum of their expected values.
# 4 The Geometric Distribution
A random variable $X$ has a geometric distribution with parameter $p$ if $p(X=k)=(1-p)^{k-1}p$ for $k=1,2,3\dots,$ where $p$ is a real number with $0\le p \le 1$. 

If the random variable $X$ has the geometric distribution with parameter $p$, then $E(X)=1/p$. 
# 5 Independent Random Variables
The random variables $X$ and $Y$ on a sample space $S$ are independent if
$$
p(X=r_1 \text{ and } Y=r_2)=p(X=r_1)\cdot p(Y=r_2)
$$
or in words, if the probability that $X=r_1$ and $Y=r_2$ equals the product of the probabilities that $X=r_1$ and $Y=r_2$, for all real numbers $r_1$ and $r_2$. 

If $X$ and $Y$ are independent random variables on a sample space $S$, then $E(XY)=E(X)E(Y)$.
# 6 Variance
The expected value of a random variable tells us its average value, but nothing about how widely its values are distributed.

Let $X$ be a random variable on a sample space $S$. The variance of $X$, denoted by $V(X)$, is 
$$
V(X)=\sum_{s \in S}(X(s)-E(X))^2p(s).
$$
That is, $V(X)$ is the weighted average of the square of the deviation of $X$. The standard deviation of $X$, denoted $\sigma (X)$, is defined to be $\sqrt{V(X)}$.

If $X$ is a random variable on a sample space $S$, then $V(X)=E(X^2)-E(X)^2$.
# 7 Chebyshev's Inequality
How likely is it that a random variable takes a value far from its expected value? Chebyshev's inequality provides an upper bound on the probability that the value of a random variable differs from the expected value of the random variable by more than a specified amount.

Let $X$ be a random variable on a sample space $S$ with probability function $p$. If $r$ is a positive real number, then
$$
p(|X(s)-E(X)|\ge r)\le V(X)/r^2.
$$
## 7.1 Example
Suppose that $X$ is the random variable that counts the number of tails when a coin is tossed $n$ times. Note that $X$ is the number of successes when $n$ independent Bernoulli trials, each with probability of succes $1/2$, are formed. It follows that $E(X)=n/2$ (by [[#2.2 Theorem 2]]) and $V(X)=n/4$. Applying Chebyshev's inequality with $r=\sqrt{n}$ shows that
$$
p(|X(s)-n/2| \ge \sqrt{n})\le (n/4)/(\sqrt{n})^2=1/4
$$
This means that the probability is no more than 1/4 that the number of tails comes up when a coin is tossed $n$ times deviates from the mean by more than $\sqrt{n}$.