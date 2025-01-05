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
\begin{aligned}
100 &= 2 \cdot 2 \cdot 5 \cdot 5=2^25^2, \\
641 &= 641, \\
999 &= 3 \cdot 3 \cdot 3 \cdot 37=3^3 \cdot 37, \\
1024 &= 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 \cdot 2 = 2^{10}
\end{aligned}
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
# 4 Theorems
## 4.1 Theorem 1
Let $a,b,$ and $c$ be integers, where $a \not = 0$. Then
$$
\begin{aligned}
(i) &\quad \text{if } a \mid b \text{ and } a \mid c, \text{ then } a \mid (b+c); \\
(ii) &\quad \text{if } a \mid b \text{ and } a \mid bc \text{ for all integers c}; \\
(iii) &\quad \text{if } a \mid b \text{ and } b \mid c, \text{ then } a \mid c. \\
\end{aligned}
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