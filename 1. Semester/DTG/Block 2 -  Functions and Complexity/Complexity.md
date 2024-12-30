# Big-$O$ Notation
Big-$O$ notation describes the growth of functions i.e. how many more operations a function has to do, depending on how big the input is. 

Let $f$ and $f$ be functions from the set of integers or the set of real numbers to the set of real numbers. We say that $f(x)$ is $O(g(x))$ if there are constants $C$ and $k$ such that $\left| f(x) \right| \le C \left| g(x) \right|$ whenever  $x>k$. 

This is read as "$f(x)$ is big-oh of $g(x)$".

The definition that $f(x)$ is $O(g(x))$ says that $f(x)$ grows slower than some fixed multiple of $g(x)$ as $x$ grows without bound.

The constans $C$ and $k$ in the big-$O$ notation are called *witnesses* to the relationship $f(x)$ is $O(g(x))$. 

When figuring out the Big-$O$ or the *growth* of a polynomial, you have to look at the "largest" $x$ i.e. the $x$ with the highest power. E.g. for $2x^4 + x^3 + 4x^2 + x + 3$, the growth or the Big-$O$ would be $O(x^4)$. 

It holds that the witness $C$ is a constant which means that we don't write $O(2x^4)$, we can leave out the $2*$, and instead define $C=2$. In other words, $C$ is used as the factor for which we multiply the growth for the complexity to hold. 

The witness $k$ is the threshold for $x$ (or $n$), for which the complexity holds. E.g. if $k=1$, then $x$ must be above $1$, for the complexity to be true.
![The function f(x) is O(g(x))](3420.png)

>[!NOTE] Theorem 1
> * Let $f(x)=a_n x^n + a_{n-1} x^{n-1}+ \cdots + a_1 x + a_0$ where $a_0, a_1, \ldots a_{n-1}, a_n$ are real numbers. Then $f(x)$ is $O(x^n)$
## Examples
1. 
Let $b>1$ then $n \le b^n \Rightarrow log_b(n) \le n$
$log_b(n) \in O(n), C=1, k=0$, because
$$ 
\begin{aligned}
log_b(b^n) &= \\
n*log_b(b) &= n
\end{aligned}
$$
2. 
$n!=1*2 \cdots n \le n^n$
$n! \in O(n^n), C=1, k=1$
3. 
Let $b>1$ then
$$ 
\begin{aligned}
log_b(n!) &= log_b(1 * 2 \cdots n) \\
&= log_b(1)+log_b(2) + \cdots log_b(n) \\
&\le n*log_b(n)
\end{aligned}
$$
$log_b(n!) \in O(n*log_b(n)), C = 1, k = 1$

![[86778.png]]
# Sums of Functions
Let $f_1 \in O(g_1)$ and $f_2 \in O(g_2)$, with witnesses $C_1, k_1$ and $C_2, k_2$. This means
$$ 
\begin{aligned}
\left| f_1(x) \right| \le C_1 \left| g_1(x) \right| \;\;\;\; \text{for } x > k_1, \\
\left| f_2(x) \right| \le C_2 \left| g_2(x) \right| \;\;\;\; \text{for } x > k_2.
\end{aligned}
$$
Then we have
$$
\begin{aligned}
    \left|f_1(x) + f_2(x)\right| &\leq \left|f_1(x)\right| + \left|f_2(x)\right| \\
    &\leq C_1 \left|g_1(x)\right| + C_2 \left|g_2(x)\right| \\
    &\leq C_1 \left|g(x)\right| + C_2 \left|g(x)\right| \quad \text{when } x > \max\{k_1, k_2\} \\
    &= (C_1 + C_2) g(x) \quad \text{where } g(x) = \max\{g_1(x), g_2(x)\}
\end{aligned}
$$
Hence $(f_1+f_2)(x) \in O(g(x))$.

## Examples
$$ 
\begin{aligned}
f_1(x) &= 3x^2 + x + 9 \\
f_2(x) &= 4x^3 + 2x^2 + 3x \\
f_1(x)+f_2(x) &= (3x^2+x+9)+(4x^3+2x^2+3x) \\
&= 3x^2+x+9+4x^3+2x^2+3x \\
&= 4x^3+6x^2+4x+9 \\\\
(f_1+f_2)(x) &\in O(x^3)
\end{aligned}
$$
This holds because the highest power of $x$ in the sum of the functions is 3. 
>[!NOTE] Theorem 2
> * Suppose that $f_1(x)$ is $O(g_1(x))$ and that $f_2(x)$ is $O(g_2(x))$. Then $(f_1+f_2)(x)$ is $O(g(x))$, where $g(x)=max(\left| g_1(x) \right|, \left| g_2(x) \right|))$ for all $x$.
# Product of Functions
Let $f_1 \in O(g_1)$ and $f_2 \in O(g_2)$, with witnesses $C_1, k_1$ and $C_2, k_2$. This means
$$
\begin{aligned}
\left| f_1(x) \right| \leq C_1 \left| g_1(x) \right| \quad \text{for } x > k_1, \\
\left| f_2(x) \right| \leq C_2 \left| g_1(x) \right| \quad \text{for } x > k_2.
\end{aligned}
$$
Then we have
$$ 
\begin{aligned}
\left| f_1(x)f_2(x) \right| &= \left| f_1(x) \right| \left| f_2(x) \right| \\
&\leq C_1 \left| g_1(x) \right|C_2 \left| g_2(x) \right| \quad \text{when } x > \max\{k_1, k_2\} \\
&= C_1 C_2 \left| g_1(x) g_2(x) \right|
\end{aligned}
$$
Hence $(f_1 f_2)(x) \in O((g_1 g_2)(x))$.
## Examples
$$ 
\begin{aligned}
f_1(x) &= 3x^2 + x + 9 \\
f_2(x) &= 4x^3 + 2x^2 + 3x \\
f_1(x)f_2(x) &= (3x^2+x+9)(4x^3+2x^2+3x) \\
&= 12x^5+6x^4+9x^3+4x^4+2x^3+3x^2+36x^3+18x^2+27x \\
&= 12x^5+10x^4+47x^3+21x^2+27x \\\\
(f_1 f_2)(x) &\in O(x^5)
\end{aligned}
$$
This holds since the highest power of $x$ is 5 in the product of the two functions.


>[!NOTE] Theorem 3
> * Suppose that $f_1(x)$ is $O(g_1(x))$ and $f_2(x)$ is $O(g_2(x))$. Then $(f_1 f_2)(x)$ is $O(g_1(x)g_2(x))$.

> [!NOTE] Theorem 4
> Let $f(x)=a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0$, where $a_0, a_1, \ldots, a_n$ are real nmbers with $a_n \neq 0$. Then $f(x)$ is of order $x^n$
# Big-Omega and Big-Theta Notation
Big-$O$ notation is used to describe the growth of functions, but it has limitations. When $f(x)$ is $O(g(x))$, we have an upper bound, in terms of $g(x)$, for the size of $f(x)$ for large values of $x$. 

Big-$O$ notation does not provide a lower bound, for this we use *big-Omega*, denoted by big-$\Omega$. 

When we want to give both an upper and a lower bound on the size of a function, we use big-Theta notation, denoted by big-$\Theta$ 

When $f(x)$ is $\Theta (g(x))$, it is also the case that $g(x)$ is $\Theta (f(x))$. $f(x)$ is $\Theta(g(x))$ if and **only if** $f(x)$ is $O(g(x))$ **and** $g(x)$ is $O(f(x))$. 
# Algorithm
An algorithm is a finite sequence of precise instructions for performing a computation or solving a problem.

We use complexity to describe how efficient an algorithm is because speed is too dependent on hardware/software. Complexity can be measured by the time / number of operations it uses or the space it takes up i.e. how much memory it uses.
# Algorithms
> An *algorithm* is a finite sequence of precise instructions for performing a computation or for solving a problem.
# Complexity of Algorithms
## Time Complexity
The time complexity of an algorithm can be expressed in terms of the number of operations used by the algorithm when the input has a particular size.
### Best, Average and Worst Case
Depending on the algorithm, it may have a different number of operations depending on multiple factors. E.g. When using a sorting algorithm, it may be that the unsorted list i.e. the input already is sorted. This situation would be the best case, as the algorithm would only have to do the checks to see if every item is sorted, rather than actually moving around elements. 

Another example could be searching algorithms. A common one is "Linear Search", which iterates through a list, doing a check each item, until it finds the correct element. This algorithm could have a different number of operations depending on where the item is in the list. E.g. if it is the first item of the list, only one operation is done - the check. If the item is not in the list, however, then it would take $2n$ + 2 checks (two checks for each item it iterates through, one for checking if the end of the list is reached, and one for checking if the element is the right one). 

Calculations can be done to find the best, average and worst cases for algorithms, i.e. the Big-Omega, Big-Theta and Big-O. 

#### Examples
Calculating the linear search algorithm can be done the following way.
- We assume $x$ is in the list.
- Equal chance for $x$ to be any of the elements.
- Hence, each with probability $\dfrac{1}{n}$, we neid either 1 or 2 or $\cdots$ or $n$ comparisons.
- We sum up to get $\dfrac{1 + \cdots + n}{n} = \dfrac{n^2 + n}{2n} = \dfrac{1}{2}n + \dfrac{1}{2} \in \Theta(n)$

| Complexity                 | Terminology             |
| -------------------------- | ----------------------- |
| $\Theta(1)$                | Constant complexity     |
| $\Theta(log(n))$           | Logarithmic complexity  |
| $\Theta(n)$                | Linear complexity       |
| $\Theta(n*log(n))$         | Linearithmic complexity |
| $\Theta(n^b)$              | Polynomial complexity   |
| $\Theta(b^n)$, where $b>1$ | Exponential complexity  |
| $\Theta(n!)$               | Factorial complexity    |
# Definitions
## Triangle Inequality
If $f(x)$ and $g(x)$ are functions, then the triangle inequality states:
$$
\left| f(x) + g(x) \right| \le \left| f(x) \right| + \left| g(x) \right|
$$
## Big-$O$
Let $f, g: \mathbb{R} \rightarrow \mathbb{R}$ (or $f,g: \mathbb{N} \rightarrow \mathbb{R}$) be two functions. We write $f(x) \in O(g(x))$ if there are constants $C, k$ such that 
$$
\left| f(x) \right| \le C \left| g(x) \right| \;\;\;\;\; \forall x > k
$$

## Big-Omega
### Book Definition
Let $f$ and $g$ be functions from the set of integers or the set of real numbers to the set of real numbers. We say that $f(x)$ is the $\Omega (g(x))$ if there are constants $C$ and $K$ with $C$ positive such that $\left| f(x) \right| \ge C \left| g(x) \right|$ whenever $x > k$

### Class Definition
Let $f,g:\mathbb{R} \rightarrow \mathbb{R}$ or (or $f,g:\mathbb{N} \rightarrow \mathbb{R}$) be two functions. We write $f(x) \in \Omega (g(x))$ if there are constraints $C > 0, k$ such that
$$
\left| f(x) \right| \geq C \left| g(x) \right| \quad \forall x > k.
$$
We say $f$ is big-Omega of $g$.

$f \in \Omega (g)$ if and only if $g \in O(f)$.

## Big-Theta
### Book Definition
Let $f$ and $g$ be functions from the set of integers or the set of real numbers to the set of real numbers. We say that $f(x)$ is $\Theta (g(x))$ if $f(x)$ is $O(g(x))$ and $f(x)$ is $\Omega (g(x))$. When $f(x)$ is $\Theta (g(x))$, we say that $f$ is big-Theta of $g(x)$, that $f(x)$ is of order $g(x)$, and that $f(x)$ and $g(x)$ are of the *same order*.
### Class Definition
Let $f,g: \mathbb{R \rightarrow R}$ (or $f,g: \mathbb{N \rightarrow R}$) be two functions. We write
$f(x) \in \Theta (g(x))$ if
$$
f(x) \in O(g(x)) \quad \text{and} \quad f(x) \in \Omega (g(x))
$$
We say $f$ is big-Theta of $g$ or $f$ and $g$ are of the same order.
> [!NOTE] IMPORTANT
> Big-Theta is often used when describing the complexity of algorithms which have the same upper- and lower bound. E.g. A "findMax" algorithm which, no matter the order of the elements in the list, would have to check all of the elements i.e. a time complexity of  $\Theta (n)$. 
## Tractability
A problem that is solvable using an algorithm with polynomial (or better) worst-case complexity is called *tractable*. If problems cannot be solved with worst-case polynomial time, they are called *intractable*.