In this workshop we will analyse some conditions for an IF statement. In the
accompanying file you can see the code and the IF statement in question.
We are looking for a big natural number x, that fulfills certain condi-
tions. To describe these conditions we introduce the following propositional
functions:
$$ 
\begin{align}
P (x) &: \text{x is a prime} \\
Q(x) &: \gcd(x, 2) = 1 \\
R(x) &: 9^x−2 \bmod 5 = 2
\end{align}
$$

We are looking for numbers x for which the following proposition is true:
$$ 
\begin{align}
(P (x) \wedge \neg R(x)) \vee \neg(P (x) \vee \neg Q(x) \vee R(x)) \vee (\neg P(x) \wedge \neg Q(x) \wedge R(x)). \\
&(1)
\end{align}
$$

For now we only know that 2 fulfills this condition. Since $P (2)$ is true, 2 is a
prime, and $Q(2)$ is false, since $\gcd(2, 2) = 2 \neq 1$, and $R(2)$ is false, because
$9^2-2 \bmod 5=79 \bmod 5=4$. Hence we get
$$ 
\begin{align}
&\quad (P(2) \wedge \neg R(2)) \vee \neg (P(2) \vee Q(2) \vee R(2)) \vee (\neg P(2) \wedge \neg Q(2) \wedge R(2)) \\
&\equiv (\mathbb{T} \wedge \neg \mathbb{F}) \vee \neg(\mathbb{T} \vee \neg \mathbb{F} \vee \mathbb{F}) \vee (\neg \mathbb{T} \wedge \neg \mathbb{F} \wedge \mathbb{F}) \\
&\equiv (\mathbb{T} \wedge \mathbb{T}) \vee \neg(\mathbb{T} \vee \mathbb{T} \vee \mathbb{F}) \vee (\mathbb{F} \wedge \mathbb{T} \wedge \mathbb{F}) \\
&\equiv \mathbb{T} \vee \neg \mathbb{T} \vee \mathbb{F} \\
&\equiv \mathbb{T} \\
\end{align}
$$

Assume we are interested in finding large numbers for which the condition is true. More precisely we would like to find three numbers $\{x, y, z\}$, where $100000 < x, y, z \leq 1000000$ that all fulfill the given condition.
# Exercise 1
## 1. How many ways can we choose $\{x, y, z\}$, where $100.000 < x, y, z \leq 1.000.000$

### a) if we do not require them to be necessarily all different?

For each of the spots $x,y,z$, we will have $1.000.000-100.000=900.000$ different possibilities, therefore the number of different ways to choose the numbers would be $900000^3$

### b) if we want them to be pairwise diffrent?
Because $x,y,z$ are distinct and labeled, the order matters. This means that this is a permutation problem i.e. we want to find $P(900000, 3)$ which can be done with the formula 
$$
P(n,r)=\dfrac{n!}{(n-r)!}
$$
Which leads us to 
$$
P(900000,3)=\dfrac{900000!}{(900000-3)!}=\dfrac{900000!}{899997!}=900000 \cdot 899999 \cdot 899998
$$
2. ~~Complete the accompanying code by adding the functions isPrime, is2mod5 and isGcd1 so they check the corresponding condition. (Hint for isGcd1: The function does not need to compute the gcd, but can simply check possible divisors. Hint for is2mod5: Find a way to apply the modulus throughout the calculations. Otherwise you will get much too big numbers very quickly when calculating 9x.)~~
3. ~~Try (ten) different values of x and see if you can find one that fulfills all conditions. Can you find one that makes (1) true?~~
# Exercise 2
## 1. Rewrite the condition in (1) into PDNF.

A proposition in PDNF (Principal Disjunctive Normal Form) is the disjunction of [[Logic#Minterm|minterms]]. 

The first part of the proposition, $P(x) \wedge \neg R(x)$, is missing the use of $Q(x)$ for it to be a minterm. The last part $(\neg P(x) \wedge \neg Q(x) \wedge R(x))$ is already a minterm. This means that we just need to rewrite the first and second part of the proposition into minterms. 

Using De Morgan's second law $\neg(p \vee q) \equiv \neg p \wedge \neg q$, we will rewrite the second part of the proposition.
$$
\begin{align}
&\quad \neg(P (x) \vee \neg Q(x) \vee R(x)) \\[0.1cm]
&\equiv \neg P(x) \wedge \neg (\neg Q(x)) \wedge \neg R(x) \\[0.1cm]
&\equiv \neg P(x) \wedge Q(x) \wedge \neg R(x)
\end{align}
$$

Using the distributive law $p \wedge (q \vee r) \equiv (p \wedge q) \vee (p \wedge r)$ and the tautology $(Q(x) \vee \neg Q(x))$, we will add $Q(r)$ to the first part to complete the minterm, and make the proposition into proper PDNF.
$$ 
\begin{align}
&\quad P(x) \wedge \neg R(x) \\[0.1cm]
&\equiv P(x) \wedge \neg R(x) \wedge (Q(x) \vee \neg Q(x)) \\[0.1cm]
&\equiv (P(x) \wedge \neg R(x) \wedge Q(x)) \vee (P(x) \wedge \neg R(x) \wedge \neg Q)
\end{align}
$$
Now, lets put together the whole proposition:
$$ 
\begin{align}
&\quad (P (x) \wedge \neg R(x)) \vee \neg(P (x) \vee \neg Q(x) \vee R(x)) \vee (\neg P(x) \wedge \neg Q(x) \wedge R(x)). &(1) \\[0.1cm]
&\equiv (P(x) \wedge \neg R(x)) \vee (\neg P(x) \wedge Q(x) \wedge \neg R(x)) \vee (\neg P(x) \wedge \neg Q(x) \wedge R(x)) \\[0.1cm]
&\equiv (P(x) \wedge \neg R(x) \wedge Q(x)) \vee (P(x) \wedge \neg R(x) \wedge \neg Q) \vee (\neg P(x) \wedge Q(x) \wedge \neg R(x)) \vee (\neg P(x) \wedge \neg Q(x) \wedge R(x))
\end{align}
$$
## 2. How many minterms does the normalform contain? What does this mean for the corresponding truth table?

A minterm of $n$ variables is a conjunction that for each variable either contains it or its negation, but not both. 

The final normal form consists of disjunctions of 4 minterms. This does not affect the final truth table as this is just a rewrite of the proposition, which means that the final outcome should not be changed.

This approach did not yield a new value for x that makes the condition true.
But we can show that $Q(x)$ and $R(x)$ are related properties.

# Exercise 3
## 1. Prove the following theorem: Let $x$ be a positive integer. It holds that $\gcd(x, 2) = 1$ if and only if $x$ is odd.

Let's call the proposition $\gcd(x,2)=1$ $P(x)$ and "$x$ is odd" $Q(x)$. Then, we could write the theorem as $\forall x (P(x) \leftrightarrow Q(x))$ whenever $x$ is a positive integer. i.e. "$P(x)$ if and only if $Q(x)$". 

I will be using a direct proof for this theorem, therefore I assume $Q(x)$ to be true. By the definition of an odd number it follows that $n=2k+1$, where $k$ is some integer.

We now try inserting an odd number $n=2k+1$ into the proposition $P(x)$.

$P(2k+1)=\gcd (2k+1, 2)$. We will use [[Number Theory#3.4 The Euclidean Algorithm|the Euclidean algorithm]] to find the gcd.

$$\gcd(2k+1, 2) = 2 \cdot 1 + 1 \Rightarrow \gcd (1,2)=1$$
As two goes into $2k+1$ one time with a remainder of 1, we then know that $\gcd(2k+1,1) \equiv \gcd(1,2)$ by the Euclidean algorithm. The greatest common divisor of 1 and 2 is 1. This concludes the direct proof of $Q(x) \rightarrow P(x)$. 

To prove the missing direction $P(x) \rightarrow Q(x)$, I will use proof by contradiction, which means that we will assume that $\gcd(x,2)=1$ when $x$ is even i.e. $P(2k)=\gcd(2k,2)=1$.
Here, we can tell that 2 divides two, meaning that the greatest common divisor is 2, disproving our assumption that $\gcd(x,2)=1$ when $x$ is even. This concludes my proof by contradiction and my direct proof, showing that $\forall x (P(x) \leftrightarrow Q(x))$ holds whenever $x$ is a positive integer.

## 2. Prove the following theorem: Let $x$ be a positive integer. It holds that $9^x−2 \bmod 5 = 2$ is equivalent to $x$ being odd.

Let's call the proposition $9^x-2 \bmod 5 = 2$ $P(x)$ and "$x$ is odd" $Q(x)$. We have to prove that $P(x) \equiv Q(x)$ when $x$ is a positive integer.

First we have to prove that if $Q(x)$, then $P(x)$ holds. Then we have to prove that if $P(x)$ then $Q(x)$ holds. 

We know that $a \bmod b = c \Rightarrow a \equiv c \pmod b$ 

Part 1:
Rewrite $9^x -2 \bmod 5 = 2$ as $9^x -2 \equiv 2 \pmod 5$. This can then be simplified as $9^x \equiv 4 \pmod 5$ by adding 2 to both sides of the equivalence. By the equivalence, $9^x \equiv 4 \pmod 5$, we know that we can substitute 4 with 9 and get $4^x-2 \equiv 2 \pmod 5$. Now, if we simplify this we get $4^x \equiv 4 \pmod 5$.

If we try inserting different values for $x$:
- $4^1 \equiv 4 \pmod 5$,
- $4^2 \equiv 1 \pmod 5$,
- $4^3 \equiv 4 \pmod 5$,
- $4^4 \equiv 1 \pmod 5$.
We can tell a pattern emerges, where when $x$ is even, $4^x\equiv 1 \pmod 5$ and when $x$ is odd, $4^x \equiv 4 \pmod 5$.
Since we know that $9^x-2 \equiv 2 \pmod 5 \Rightarrow 4^x\equiv 4 \pmod 5$, we can tell that $x$ is odd, proving the first part of the equivalence.

Part 2:
We know that if $x$ is odd, then $4^x \equiv 4 \pmod 5$. Furthermore we know that the proposition $9^x-2 \bmod 5 =2$ can be rewritten as $4^x \equiv 4 \pmod 5$. This concludes the proof.
## 3. Explain why the previous theorems show that $Q(x)$ and $R(x)$ are the same function. Hence we can replace $R(x)$ with $Q(x)$ in (1) and show that it is equivalent to
$$ 
\begin{align}
&\quad (P(x) \wedge \neg Q(x)) \vee \neg (P(x) \vee \neg Q(x) \vee Q(x)) \vee (\neg P(x) \wedge \neg Q(x) \wedge Q(x)) \\
&\equiv (P(x) \wedge \neg Q(x)) \vee \neg (P(x) \vee \mathbb{T}) \vee (\neg P(x) \wedge \mathbb{F}) \\
&\equiv P(x) \wedge \neg Q(x) &(2)
\end{align}
$$
Based on the proofs in tasks 3.1, 3.2, we know that both $Q(x)$ and $R(x)$ are equivalent to $x$ being odd. This means that they are the same function, making them interchangeable. 

## 4. Check if (2) is in CNF, DNF, PCNF and PDNF.

[[Logic#Conjunctive Normal Form|CNF]] is a proposition consisting of conjunctions of elementary disjunctions, hence $P(x) \wedge \neg Q(x)$ is in not in CNF, it is an elementary conjunction.

[[Logic#Disjunctive Normal Form|DNF]] is a proposition consisting disjunctions of elementary conjunctions. If the second part of the original proposition (2) had been left out, then it would have been in DNF, but because the second part is a disjunction, the proposition is not in DNF.

[[Logic#Principal Conjunctive Normal Form|PCNF]] is a proposition consisting of conjunctions of [[Logic#Maxterm|maxterms]]. No maxterms appear in the proposition (2), therefore it is not in PCNF

[[Logic#Principal Disjunctive Normal Form|PDNF]] is a proposition consisting of disjunctions of [[Logic#Minterm|minterms]]. The only minterm appearing in the proposition is the first part, $(P(x) \wedge \neg Q(x))$. The other parts are not minterms and therefore the proposition is not in PDNF.

We have discovered that the condition is equivalent to x being a prime and $\gcd(x, 2) \neq 1$.
# Exercise 4
## 1. Formulate a proof by contradiction that shows that for all integers $x > 2$ the proposition $(P(x) \wedge \neg Q(x))$ is false. Hence show the following: Let $x > 2$ be an integer. Then $x$ can not be a prime and $\gcd(x, 2) \neq 1$.

Forming a proof by contradiction, we have to prove the opposite of the statement i.e. that when $x > 2$, the proposition $(P(x) \wedge \neg Q(x))$ is true. 

As we know by the definition of an odd number $n=2k+1$, every other number is odd. If $\gcd(x,2) \neq 1$ is to be true, then by our earlier proof of $Q(x)$,  $x$ would have to be a factor of 2. i.e. not odd. This is the proof by contradiction of $\neg Q(x)$. By this, we know that for $\neg Q(x)$ to be true, then the number has to be even and as we know, no even numbers above 2 are prime. This means that not both $P(x)$ and $\neg Q(x)$ can be true, making the proposition false when $x > 2$, concluding our proof by contradiction.