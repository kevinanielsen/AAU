# 1 Divisibility
> Division of an integer by a positive integer produces a quotient and a remainder

When one integer is divided by a second nonzero integer, the quotient may or may not be an integer. For example, $12/3=4$ is an integer, whereas $11/4=2.75$ is not.

If $a$ and $b$ are integers with $a \neq 0$, we say that $a$ *divides* $b$ if there is an integer $c$ such that $b=ac$ (or equivalently, if $\dfrac{b}{a}$ is an integer). When $a$ divides $b$ we say that $a$ is a *factor* or *divisor* of $b$, and that $b$ is a multiple of $a$. The notation $a \mid b$ denotes that $a$ divides $b$. We write $a \nmid b$ when $a$ does not divide $b$.

Using quantifiers we can express $a \mid b$ as $\exists c (ac=b)$. 
## 1.1 The Division Algorithm
$d$ is called the *divisor*, $a$ is called the *dividend*, $q$ is called the *quotient*, and $r$ is called the *remainder*.  We use this notation to express the quotient and remainder:
$$
q=a \textbf{ div } d, \quad r = a \bmod d.
$$
## 1.2 Modular Arithmetic
In some situations we care only about the remainder of an integer when it is divided by some specified positive integer. Here, we use the modulus operator, denoted by $a \mod b$ or sometimes $a \; \% \; b$ in computer science.

If $a$ and $b$ are integers and $m$ is a positive integer, then $a$ is *congruent* to $b$ *modulo* $m$ if $m$ divides $a-b$. We use the notation $a \equiv b \pmod m$ to indicate that $a$ is congruent to $b$ modulo $m$. We say that $a \equiv b \pmod m$ is a *congruence* and that $m$ is its *modulus* (plural *moduli*). If $a$ and $b$ are not congruent modulo $m$, we write 
$a \not\equiv b \pmod{m}$.
### 1.2.1 Example
Determine whether 17 is congruent to 5 modulo 6 and whether 24 and 14 are congruent modulo 6.
#### 1.2.1.1 Solution 
Because 6 divides $17−5= 12$, we see that $17 \equiv 5 \pmod{6}$. However, because $24−14= 10$ is not divisible by 6, we see that $24 \not\equiv 14 \pmod 6$.
## 1.3 Arithmetic Modulo $m$
We can define arithmetic operations on $\mathbf{Z}_m$, the set of nonnegative integers less than $m$, that is, the set $\{0,1, \ldots,m-1\}$. In particular, we define addition of these integers, denoted by $+_m$ by 
$$
a+_mb=(a+b)\bmod m,
$$
where the addition on the right-hand side of this equation is the ordinary addition of integers, and we define multiplication of these integers, denoted by $\cdot_m$ by
$$
a \cdot_m=(a \cdot b) \bmod m,
$$
where the multiplication on the right-hand side of this equation is the ordinary multiplication of integers. The operations $+_m$ and $\cdot_m$ are called addition and multiplication modulo $m$ and when we use these operations, we are said to be doing *arithmetic modulo* $m$.
# 2 Primes
> Positive integers that have exactly two different positive integer factors are called *primes*. A positive integer that is greater than 1 and is not prime is called *composite*

***Remark:*** The integer 1 is not prime, because it has only one positive factor. 
## 2.1 The Fundamental Theorem of Arithmetic
Every integer greater than 1 can be written uniquely as a prime or as the product of two or more primes, where the prime factors are written in order of nondecreasing size.
### 2.1.1 Examples
$$ 
\begin{align}
100 &= 2 \cdot 2 \cdot 5 \cdot 5=2^25^2, \\
641 &= 641, \\
999 &= 3 \cdot 3 \cdot 3 \cdot 37=3^3 \cdot 37, \\
1024 &= 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 = 2^{10}
\end{align}
$$
## 2.2 Trial Division
To show that a given integer is prime, you can use *trial division*. One procedure is using the following theorem:
If $n$ is a composite integer, then $n$ has a prime divisor less than or equal to $\sqrt{n}$. 
### 2.2.1 Examples
1. ***Show that 101 is prime.***
The only primes not exceeding $\sqrt{101}$ are 2, 3, 5, and 7. Because 101 is not divisible by either of these, it follows that 101 is prime.
2. ***Find the prime factorization of 7007.***
To find the factorization of 7007, first perform divisions of 7007 by succesive primes, beginning with 2. The lowest prime that divides 7007 is 7, with $7007/7=1001$. Next, divide 1001 by successive primes, beginning with 7. 7 Also divides 1001, with $1001/7=143$. 7 does not divide 143, 11 does divide 143, with $143/11=13$. Because 13 is prime, the procedure is completed. It follows that $7007=7 \cdot 1001 = 7 \cdot 7 \cdot 143 = 7 \cdot 7 \cdot 11 \cdot 13$. Consequently, the prime factorization of 7007 is $7 \cdot 7 \cdot 11 \cdot 13 = 7^2 \cdot 11 \cdot 13$.
## 2.3 The Sieve of Eratosthenes
Composite integers not exceeding 100 must have a prime factor not exceeding 10. Because the only primes less than 10 are 2, 3, 5, or 7. 

The sieve of Eratosthenes is used to find all primes not exceeding a specified positive integer. For instance, the following procedure is used to find the primes not exceeding 100. 
![[35391.png]]
# 3 Greatest Common Divisors
> Let $a$ and $b$ be integers, not both zero. The largest integer $d$ such that $d \mid a$ and $d \mid b$ is called the *greatest common divisor* of $a$ and $b$. The greatest common divisor of $a$ and $b$ is denoted by $\gcd(a,b)$. 

The greatest common divisor of two integers, not both zero, exists because the set of common divisors of these integers is nonempty and finite. One way to find the greatest common divisor of two integers is to find all the positive common divisors of both integers and then take the largest divisor.
## 3.1 Relative Prime
The integers $a$ and $b$ are *relatively prime* if their greatest common divisor is 1.

The integers $a_1, a_2, \ldots, a_n$ are *pairwise relatively prime* if $\gcd(a_i, a_j)=1$ whenever $1 \leq i \leq j \leq n$. 
### 3.1.1 Examples
1. The integers 17, 22 are relatively prime as $\gcd(17, 22)=1$
2. The integers 10, 17 and 21 are *pairwise relatively prime* as $\gcd(10, 17)=1, \gcd(10,21)=1$, and $\gcd(17,21)=1$.
## 3.2 Least Common Multiple
The least common multiple of the positive integers $a$ and $b$ is the smallest positive integer that is divisible by both $a$ and $b$. The least least common multiple of $a$ and $b$ is denoted by $\text{lcm}(a,b)$. 

Suppose that the prime factorizations of $a$ and $b$ are as before. Then the least common multiple of $a$ and $b$ is given by
$$
\text{lcm}(a,b)=p_1^{max(a_1,b_1)}p_2^{max(a_2,b_2)}\cdots p_n^{max(a_n,b_n)},
$$
where $\max(x,y)$ denotes the maximum of the two numbers $x$ and $y$.

Another method for finding the $\text{lcm}(a,b)$ is by dividing $ab$ with $\gcd(a,b)$ i.e.
$$
\text{lcm}(a,b)=\dfrac{ab}{\gcd(a,b)}
$$
### 3.2.1 Example
*What is the least common multiple of $2^33^57^2$ and $2^43^3$?***
We have
$$
\text{lcm}(2^23^57^2,2^43^3)=2^{\max(3,4)}3^{\max(5,3)}7^{\max(2,0)}=2^43^57^2
$$
Let $a$ and $b$ be positive integers. Then
$$
ab = \gcd(a,b) \cdot \text{lcm}(a,b).
$$
## 3.3 Examples
1. ***What is the greatest common divisor of 24 and 36?***
The positive common divisors of 24 and 36 are 1, 2, 3, 4, 6, 12. Hence $\gcd(24, 36) = 12$.
## 3.4 The Euclidean Algorithm
The Euclidean algorithm is an efficient method of finding the greatest common divisor.

Let $a=bq+r$, where $,b,q,$ and $r$ are integers. Then $\gcd(a,b)=\gcd(b,r)$.
### 3.4.1 Examples
1. ***Find the greatest common divisor of 91 and 287***
First, divide 287, the larger of the two integers, by 91, the smaller, to obtain 
$$
287=91 \cdot 3+14
$$
Any divisor of 91 and 287 must also be a divisor of $287-91 \cdot 3 = 14$. Hence, the greatest common divisor of 91 and 287 is the same as the greatest common divisor of 91 and 14. This means that the problem of finding $\gcd(91, 287)$ has been reduced to finding $\gcd(91,14)$.
Next, divide 91 by 14 to obtain
$$
91=14 \cdot 6 + 7
$$
Because any common divisor of 91 and 14 also divides $91-14 \cdot 6 = 7$ and any common divisor of 14 and 7 divides 91, it follows that $\gcd(91,14) = \gcd(14,7)$. Continue by dividing 14 by 7, to obtain
$$
14 = 7 \cdot 2.
$$
Because 7 divides 14, it follows that $\gcd(14,7)=7$. Furthermore, because $\gcd(287,91)=\gcd(91,14)=\gcd(14,7)=7$, the original problem has been solved.
## 3.5 gcds as Linear Combinations
The greatest common divisor of two integers $a$ and $b$ can be expressed in the form
$$
sa+tb,
$$
where $s$ and $t$ are integers. In other words, $\gcd(a,b)$ can be expressed as a *linear combination* with integer coefficients of $a$ and $b$. For example, $\gcd(6,14)=2$, and $2=(-2) \cdot 6 + 1 \cdot 14$.
This theorem is called "Bézout's Theorem":
If $a$ and $b$ are positive integers, then there exists integers $s$ and $t$ such that $\gcd(a,b)=sa+tb$. The integers $s$ and $t$ are called *Bézout coefficients* of $a$ and $b$.
# Applications of Congruences
## Hashing Functions
A hashing function $h$ assigns memory location $h(k)$ to the record that has $k$ as its key.
One of the most common hashing functions is
$$
h(k)=k \bmod m
$$
where $m$ is the number of available memory locations.
Hashing functions should be easily evaluated so that files can be quickly located. The hashing function $h(k)=k \bmod m$ meets this requirement; to find $h(k)$, we need only compute the remainder when $k$ is divided by $m$. Furthermore, the hashing function should be [[Functions#3.3 Onto / Surjection|onto]], so that all memory locations are possible. The function $h(k)=k \bmod m$ also satisfies this property.

Because hashing functions are not [[Functions#3.2 One-to-One Functions / Injection|one-to-one]] (because there are more possible keys than memory locations), more than one file may be assigned to a memory location. We call this a *collision*. 
### The Linear Probing Function
To avoid collisions, we can use a *linear probing function*, that looks for the first free memory location if the "spot" is already taken. This function can be described with $h(k,i)=h(k)+i \bmod m$, where $i$ runs from 0 to $m-1$. 
## Pseudorandom Numbers
Because numbers generated by systematic methods are not truly random (although they contain properties of randomly chosen numbers), they are called *pseudorandom numbers*.
### The Linear Congruential Method
The most common way of generating pseudorandom numbers is the *linear congruential method*. This works by choosing 4 integers: the *modulus* $m$, *multiplier* $a$, *increment* $c$, and *seed* $x_0$, with $2 \leq a < m, 0 \leq c < m$, and $0 \leq x_0 < m$. We generate a sequence of pseudorandom numbers $\{x_n\}$, with $0 \leq x_n < m$ for all $n$, by successively using the [[Recursion#Functions|recursively defined function]]
$$
x_{n+1}=(ax_n+c) \bmod m.
$$
To generate pseudorandom numbers between 0 and 1, we divide the generated numbers by the modulus: that is, we use the numbers $x_n/m$.
### Pure Multiplicative Generator
Most computers use linear congruential generators to generate pseudorandom numbers. Often, a linear congruential generator with  increment $c=0$ is used. Such a generator is called a *pure multiplicative generator*. 
The pure multiplicative generator with modulus $2^{31}-1$ and multiplier $7^5=16,807$ is widely used. With these values, it can be shown that $2^{31}-2$ numbers are generated before repetition begins.
# 4 Theorems
## 4.1 Theorem 1
Let $a,b,$ and $c$ be integers, where $a \not = 0$. Then
$$
\begin{align}
(i) &\quad \text{if } a \mid b \text{ and } a \mid c, \text{ then } a \mid (b+c); \\
(ii) &\quad \text{if } a \mid b \text{ and } a \mid bc \text{ for all integers c}; \\
(iii) &\quad \text{if } a \mid b \text{ and } b \mid c, \text{ then } a \mid c. \\
\end{align}
$$
## 4.2 Theorem 2: The Division Algorithm
Let $a$ be an integer and $d$ a positive integer. Then there are unique integers $q$ and $r$, with $0\leq r \leq d$, such that $a=dq+r$. 
## 4.3 Theorem 3
Let $a$ and $b$ be integers, and let $m$ be a positive integer. Then $a \equiv b \pmod m$ if and only if $a \bmod m = b \bmod m$ 
## 4.4 Theorem 4
Let $m$ be a positive integer. The integers $a$ and $b$ are congruent modulo $m$ if and only if there is an integer $k$ such that $a=b+km$
## 4.5 Theorem 5
Let $m$ be a positive integer. If $a \equiv b \pmod m$ and $c \equiv d \pmod m$, then
$$
a+c \equiv b+d \!\!\! \pmod m \quad \text{and} \quad ac \equiv bd \!\!\! \pmod m.
$$
## 4.6 Fermat's Little Theorem
If $p$ is prime and $a$ is an integer not divisible by $p$, then
$$
a^{p-1} \equiv 1 \pmod{p}.
$$
Furthermore, for every integer $a$ we have
$$
a^p \equiv a \pmod p.
$$
## 4.7 The Prime Number Theorem
The ratio of $\pi(x)$, the number of primes not exceeding $x$, and $x/\ln x$ approaches 1 as $x$ grows without bound. (Here $\ln x$ is the natural logarithm of $x$.)
![[43854.png]]
### 4.7.1 Example
Find $7^{222} \bmod 11$.
We can use Fernat's little theorem to evaluate $7^{222} \bmod 11$ rather than using the fast modular exponentiation algorithm. By Fernat's little theorem we know that $7^{10} \equiv 1 \pmod{11}$, so $(7^{10})^k \equiv 1 \pmod{11}$ for every positive integer $k$. To take advantage of this last congruence, we divide the exponent 222 by 10, finding that $222=22*10+2$. We now see that
$$
7^{222}=7^{22 \cdot 10+2}=(7^{10})^{22}7^2 \equiv (1)^{22} \cdot 49 \equiv 5 \pmod{11}.
$$
It follows that $7^{222} \bmod 11 = 5$.