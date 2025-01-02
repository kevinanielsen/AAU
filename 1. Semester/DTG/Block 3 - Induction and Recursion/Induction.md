# Mathematical Induction
Mathematical induction is a proof technique. It is not a tool for discovering formulae or theorems, as it bases its proofs on results obtained in some other way. I.e. It is a tool for proving assertions.

Mathematical induction can be used to prove statements that assert that $P(n)$ is true for all positive integers $n$, where $P(n)$ is a propositional function. A proof by mathematical induction has two parts, a *basis step*, where we show that $P(1)$ is true, and an *inductive step*, where we show that for all positive integers $k$, if $P(k)$ is true, then $P(k+1)$ is true. 

## Principle of Mathematical Induction
To prove that $P(n)$ is true for all positive integers $n$, where $P(n)$ is a propositional function, we complete two steps:
### Basis Step 
We verify that $P(1)$ is true.
### Inductive Step
We show that the conditional statement $P(k) \rightarrow P(k+1)$ is true for all positive integers $k$.

To complete the inductive step, we assume that $P(k)$ is true for an arbitrary positive integer $k$, and show that under this assumption, $P(k+1)$ must also be true. This assumption, that $P(k)$ is true, is called the *inductive hypothesis*. 

One both steps are completed, we have shown that $P(n)$ is true for all positive integers $n$ i.e. that $\forall n P(n)$ is true where the quantification is over the set of positive integers.

In the inductive step, we have shown that $\forall k(P(k) \rightarrow P(k+1))$ is true, where again, the domain is the set of positive integers. This proof technique can be stated as
$$
(P(1) \wedge \forall k(P(k) \rightarrow P(k+1))) \rightarrow \forall n P(n)
$$
when the domain is the set of positive integers.

Mathematical induction be used to prove other theorems than those of the form "$P(n)$ is true for all positive integers $n$."

## Guidelines for Proofs by Mathematical Induction
1. Express the statement that is to be proved in the form "for all $n \geq b, P(n)$" for a fixed integer $b$. 
	1. For statements of the form "$P(n)$ for all positive integers $n$", let $b=1$.
	2. For statements of the form "$P(n) for all nonnegative integers $n$", let $b=0$.
	3. For some statements of the form $P(n)$, such as inequalities, you may need to determine the appropriate value of $b$ by checking the truth values of $P(n)$ for small values of $n$.
2. Write out the words "Basis Step". Then show that $P(b)$ is true, taking care that the correct value of $b$ is used. 
3. Write out the words "Inductive Step" and state, and clearly identify, the inductive hypothesis, in the form "Assume that $p(k)$ is true for an arbitrary fixed integer $k \geq b$". 
4. State what needs to be proved under the assumption that the inductive hypothesis is true. That is, write out what $P(k+1)$ says.
5. Prove the statement $P(k+1)$ making use of the assumption $P(k)$. 
6. Clearly identify the conclusion of the inductive step, such as by saying "This completes the inductive step".
7. After completing the basis step and the inductive step, state the conclusion, namely, "By mathematical induction, $P(n)$ is true for all integers $n$ with $n \geq b$".
## Examples
### Example 1
Show that if $n$ is a positive integer, then 
$$
1+2+\cdots+n=\dfrac{n(n+1)}{2}
$$
#### Basis step:
$$ 
\begin{aligned}
P(1) &\Rightarrow \\
1 &= \dfrac{1(1+1)}{2} \\
1 &= 2/2 = 1
\end{aligned}
$$
#### Inductive step
For the inductive hypothesis we assume that $P(k)$ holds for an arbitrary positive integer $k$. That is, we assume that 
$$
1+2+ \cdots + k = \dfrac{k(k+1)}{2}.
$$
Under this assumption, it must be shown that $P(k+1)$ is true, namely that
$$
1+2+\cdots+k+(k+1)=\dfrac{(k+1)[(k+1)+1]}{2}=\dfrac{(k+1)(k+2)}{2}
$$
We observe that the summation in the left-hand side of $P(k+1)$ is $k+1$ more than the summation in the left-hand side of $P(k)$. Our strategy will be to add $k+1$ to both sides of the equation in $P(k)$ and simplify the results algebraically to complete the inductive step.
We now return to the proof of the inductive step. When we add $k+1$ to both sides of the equation in $P(k)$, we obtain
$$ 
\begin{aligned}
1+2+\cdots+k+(k+1) &= \dfrac{k(k+1)}{2}+(k+1) \\
&= \dfrac{k(k+1)+2(k+1)}{2} \\
&= \dfrac{k(k+1)+2(k+1)}{2} \\
&= \dfrac{(k+1)(k+2)}{2}
\end{aligned}
$$
This last equation shows that $P(k+1)$ is true under the assumption is that $P(k)$ is true. This completes the inductive step.
### Example 2
Prove that $$1+2+2^2+\cdots+2^n=2^{n+1}-1$$ for all nonnegative integers $n$.
#### Basis Step
$P(0)$ is true because $2^0=1=2^1-1$. This completes the basis step.
#### Inductive Step
We have to assume that $P(k)$ is true for an arbitrary nonnegative integer $k$. That is, we assume that $1+2+2^2+\cdots+2^k=2^{k+1}-1$.
From there, we have to assume that $P(k+1)$ also holds true. That is, we must show that
$$
1+2+2^2+\cdots+2^k+2^{k+1}=2^{k+1+1}-1=2^{k+2}-1.
$$
Assuming the inductive hypothesis $P(k)$, we see that
$$
\begin{aligned}
1+2+2^2+\cdots+2^k+2^{k+1}&=(1+2+2^2+\cdots+2^k)+2^{k+1} \\
&=(2^{k+1}-1)+2^{k+1} \\
&= 2\cdot2^{k+1}-1 \\
&= 2^{k+2}-1
\end{aligned}
$$
### Example 3
Prove the inequality $n<2^n$ for all positive integers $n$.
#### Basis Step
$P(1)$ is true because $1<2^1 \Rightarrow 1<2$. This completes the basis step.
#### Inductive Step
We have to assume that $P(k)$ is true for an arbitrary nonnegative integer $k$. That is, we assume that $k<2^k$. 
From there, we have to assume that $P(k+1)$ also holds true. That is, we must show that
$$
k+1 < 2^{k+1}.
$$
Assuming the inductive hypothesis $P(k)$, we see that 
$$ 
\begin{aligned}
k+1 &<2^k+1 \leq 2^k+2^k =2 \cdot 2^k = 2^{k+1} \\

\end{aligned}
$$
### Example 4
Prove that $2^n<n!$ for every integer $n$ with $n \geq 4$.
#### Basis Step
Since we know that $n \geq 4$, we will do the lowest possible $n$, being 4, therefore we check that $P(4)$. $2^4<4! \Rightarrow 16<24$. This is true. 
#### Inductive Step
We have to assume that $P(k)$ is true for an arbitrary integer $k\geq 4$. That is, we assume that $2^k<k!$.
From there, we have to assume that $P(k+1)$ also holds true. That is, we must show that
$$
2^{k+1}<(k+1)!
$$
Assuming the inductive hypothesis $P(k)$, we see that 
$$ 
\begin{aligned}
2^{k+1} &= 2 \cdot 2^k \\
&< 2 \cdot k! \\
&< (k+1)k! \\
&= (k+1)!
\end{aligned}
$$
### Example 5
Use mathematical induction to prove that $n^3-n$ is divisible by 3 whenever $n$ is a positive integer.
#### Basis Step
"whenever $n$ is a positive integer" means that we will use 1 for our basis step. I.e. we have to prove $P(1)$. $1^3-1=0$, since $0/3=0$, that means that 0 is divisible by 3, proving our basis step.
#### Inductive Step
Assume that $P(k)$ is true for an arbitrary $k$. That is, we assume that $k^3-k$ is divisible by 3. Assuming that our inductive hypothesis is true, we need to prove that $P(k+1)$ is true i.e. $(k+1)^3-(k+1)$ should be divisible by 3.
$$ 
\begin{aligned}
(k+1)^3-(k+1) &= (k^2+k+1)(k+1)-(k+1) \\
&= (k^3+3k^2+3k+1) -(k+1) \\
&= (k^3-k)+3(k^2+k)
\end{aligned}
$$
Using the inductive hypothesis, we conclude that the first term $k^3-k$ is divisible by 3. The second term is divisible by 3 because it is 3 times an integer.
### Example 6
Use mathematical induction to prove that $7^{n+2}+8^{2n+1}$ is divisible by 57 for every nonnegative integer $n$. Since it is stated that his theorem holds for nonnegative integers $n$, we shall use 0 as the value for the basis step.
#### Basis Step
$$P(0)=7^{0+2}+8^{2 \cdot 0+1}=7^2+8^1=57$$
$\dfrac{57}{57}=1$, therefore our basis step holds.
#### Inductive Step
Assume that $P(k)$ is true for an arbitrary $k$. That is, we assume that $7^{k+2}+8^{2k+1}$ holds. Now, we need to prove that $P(k+1)$ is true i.e. $7^{(k+1)+2}+8^{2(k+1)+1}$ is divisible by 57.
$$
\begin{aligned}
7^{(k+1)+2}+8^{2(k+1)+1} &= 7^{k+3}+8^{2k+3} \\
&= 7 \cdot 7^{k+2}+8^2 \cdot 8^{2k+1} \\
&= 7 \cdot 7^{k+2}+64 \cdot 8^{2k+1} \\
&= 7(7^{k+2}+8^{2k+1})+57 \cdot 8^{2k+1}
\end{aligned}
$$
This holds because as we know, $7^{k+2}+8^{2k+1}$ is divisible with 57, therefore, 7 times that equation, will also be divisible with 57. Furthermore, the second part of the result is 57 times 8 to the power of $2k+1$, therefore it is also divisible with 57.
### Example 8
Verify that for all $n \geq 1$, the sum of the squares of the first $2n$ positive integers is given by the formula
$$
1^2+2^2+3^2+\cdots+(2n^2) = \dfrac{n(2n+1)(4n+1)}{3}
$$
#### Basis Step
We will use $P(1)$ to check that the formula holds.
$$
1^2+2^2=\dfrac{1(2 \cdot 1 + 1)(4 \cdot 1 + 1)}{3}=\dfrac{1(3)(5)}{3}=\dfrac{15}{3}=5
$$
#### Inductive Hypothesis
Our inductive hypothesis says that $P(k)=1^2+2^2+3^2+\cdots+(2k^2) = \dfrac{k(2k+1)(4k+1)}{3}$ 
#### Inductive Step
We assume that our inductive hypothesis $P(k)$ holds true for an arbitrary $k$. We now need to prove that $P(k+1)$ i.e. 
$$ 
\begin{aligned}
1^2+2^2+3^2+\cdots+(2(k+1)^2) &= \dfrac{(k+1)(2(k+1)+1)(4(k+1)+1)}{3} \\
&= \dfrac{(k+1)(2k+2+1)(4k+4+1)}{3} \\
&= \dfrac{(2k^2+5k+3)(4k+4+1)}{3} \\
&= \dfrac{8k^3+8k^2+2k^2+20k^2+20k+5k+12k+12+3}{3} \\
&= \dfrac{8k^3+30k^2+37k+15}{3}
\end{aligned}
$$
holds true.
$$ 
\begin{aligned}
&1^2+2^2+3^2+\cdots+(2k^2)+((2k+1)^2)+(2(k+1)^2) \\
&= \dfrac{k(2k+1)(4k+1)}{3} + (2k+1)^2+(2(k+1))^2 \\
&= \dfrac{k(2k+1)(4k+1) + 3((2k+1)^2+(2(k+1))^2)}{3} \\
&= \dfrac{(2k^2+k)(4k+1) + 3(4k^2+4k+1+(2k+2)^2)}{3} \\
&= \dfrac{8k^3+6k^2+k + 3(8k^2+12k+5)}{3} \\
&= \dfrac{8k^3+6k^2+k + 24k^2+36k+15}{3} \\
&= \dfrac{8k^3+30k^2+37k+15}{3}
\end{aligned}
$$
We started off by taking our inductive hypothesis and adding $((2k+1)^2)+(2(k+1)^2$ to it on both sides of the equation. We did this because 
$$
1^2+2^2+3^2+\cdots+(2(k+1)^2) = 1^2+2^2+3^2+\cdots+(2k^2)+((2k+1)^2)+(2(k+1)^2)
$$
This is so because the formula states that the left side is the sum of all squares up until $2n$, therefore not adding $((2k+1)^2)$ would mean skipping a number in the sum.
From there on, we just had to simplify. I simplified the statement we needed to prove $(P(k+1))$ to make things simpler in the final proof.

# Strong Induction
Strong induction is another form of induction, primarily used when we cannot easily prove a result using mathematical induction. The basis step of a proof by strong induction is the same as a proof of the same result using mathematical induction.

Strong induction is sometimes called *the second principle of mathematical induction* or *complete induction*. When the terminology "complete induction" is used, the principle of mathematical induction is called *incomplete induction*. 

## Example
Regular induction can be described using the example of the infinite ladder. Strong induction tells ut that we can reach all rungs if
1. We can reach the first rung, and
2. for every positive integer $k$, if we can reach all the first $k$ rungs, then we can reach the $(k+1)$st rung.
## Inductive Step
In the inductive step of a mathematical proof we need to show that if the inductive hypothesis $P(k)$ is true, then $P(k+1)$ is also true. In a proof by strong induction, the inductive step shows that if $P(j)$ is true for all positive integers $j$ not exceeding $k$, then $P(k+1)$ is true. That is, for the inductive hypothesis we assume that $P(j)$ is true for $j=1,2, \ldots, k$.

## Strong induction
To prove that $P(n)$ is true for all positive integers $n$, where $P(n)$ is a propositional function, we complete two steps:
### Basis step
We verify that the proposition P(1) is true.
### Inductive step
We show that the conditional statement 
$[P(1) \wedge P(2) \wedge \cdots \wedge P(k)] \rightarrow P(k +1)$ is true for all positive integers $k$.

# When to Use Each Method
In practice, you should use mathematical induction when it is straightforward to prove that $P(k) \rightarrow P(k+1)$ is true for all positive integers $k$. This is true for all the examples used in the earlier section about [[Induction#Mathematical Induction]]. In general, you should restrict your use of mathematical induction to such scenarios. Unless you can clearly see that the inductive step of a proof by mathematical induction goes through, you should attempt a proof by strong induction. 

We can adapt strong induction to handle cases where the inductive step is valid only for integers greater than a particular integer. Let $b$ be a fixed integer and $j$ a fixed positive integer. The form of strong induction we need tells us that $P(n)$ is true for all integers $n$ with $n \neq b$ if we can complete these two steps:
### Basis Step
We verify that the propositions $P(b), P(b+1), \ldots, P(b+j$ are true.
### Inductive Step
We show that $[P(b) \wedge P(b+1) \wedge \cdots \wedge P(k)] \rightarrow P(k+1)$ is true for every integer $k \geq b+j$.

## Examples
### Example 1
Prove that every amount of postage of 12 cents or more can be formed using just 4-cent and 5-cent stamps.
#### Basis Step
We can form postage of 12, 13, 14, and 15 cents using three 4-cent stamps, two 4-cent stamps and one 5-cent stamp, one 4-cent stamp and two 5-cent stamps, and three 5-cent stamps, respectively. This shows that $P(12), P(13), P(14)$, and $P(15)$ are true. This completes the basis step.
#### Inductive Step
The inductive hypothesis is the statement that $P(j)$ is true for $12 \leq j \leq k$, where $k$ is an integer with $k \geq 15$. To complete the inductive step, we assume that we can form postage of $j$ cents, where $12 \leq j \leq k$. We need to show that under the assumption that $P(k+1)$ is true, we can also form postage of $k+1$ cents. Using the inductive hypothesis, we can assume that $P(k-3)$ is true because $k-3 \leq 12$, that is, we can form postage of $k-3$ cents using just 4-cent and 5-cent stamps. To form postage of $k+1$ cents, we need only add another 4-cent stamp to the stamps we used to form postage of $k-3$ cents. That is, we have shown that if the inductive hypothesis is true, then $P(k+1)$ is also true. This completes the inductive step.