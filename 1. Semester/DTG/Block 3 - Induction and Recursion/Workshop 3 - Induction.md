In this workshop we will study the MergeSort sorting algorithm. A pseudocode for MergeSort is presented as figure 1 and can also be looked up in *Ros*, section 5.4.4. Mergesort uses a subroutine Merge, that is presented in figure 2. Note that the algorithms are described here a little diﬀerent than in *Ros*, but the underlying idea is the same. To sort a list $L = (a_0, a_1, \ldots , a_{n−1})$ with the program given in the pseudocode one would call the procedure $Mergesort(L, 0, n− 1)$. Before you start it might be useful to reacquaint yourself with section 5.4.4
![Figure 1: Mergesort](98248.png)
# ~~Exercise 1~~
1. ~~Implement Merge and MergeSort~~
2. ~~Use MergeSort to sort the list $L=(5,3,8,1,6,10,7,2,4,9)$~~
# Exercise 2
1. **Proof by using induction, that MergeSort returns the sorted list containing the same elements as the input list $L$. In the proof you may assume, that Merge returns a sorted list containing the elements of two sorted lists given as inputs.**
**Basis Step:**
When $l \geq r$, the list has 0 or 1 elements. In this case, MergeSort returns L unchanged, which is trivially sorted. 
**Inductive Hypothesis:**
Let $k \geq 1$. Assume that MergeSort correctly sorts all sublists of length $\leq k$.
**Inductive Step:**

Given a list of length $k+1$. When $MergeSort(L,l,r)$ is called:
1. It computes $m=\left\lfloor \dfrac{l+r}{2} \right\rfloor$. 
2. Since the left half is now shorter than $k+1$, by the inductive hypothesis, $MergeSort(L, l, m)$ correctly sorts the left half.
3. Since the right half is now shorter than $k+1$, by the inductive hypothesis, $MergeSort(L,m+1,r)$ correctly sorts the right half.
4. By our assumption, Merge correctly combines the two sorted halves into a fully sorted list.
# Exercise 3
In Ros it is shown that the merging of two sorted lists of lengths $a$ and $b$ can
be accomplished by using at most $a + b − 1$ comparisons (Lemma 1, section
5.4.4.).
![Figure 2: Merge](15879.png)
1. **Assume that Merge uses (exactly) $a+b-1$ comparisons to combine two lists with $a$ and $b$ elements. Furthermore, assume that the length of the input list $L$ is $n=2^k$. Prove by using induction on $k$, that Mergesort uses** $$n(log_2(n)+1)=2^k(k+1)$$
   **comparisons to sort $L$. What type of induction did you use?**
**Basis Step:** For our basis step we will set $k=0$ i.e. check that $P(0)$ holds. 
$n=2^0=1 \Rightarrow \{1\}$
In the case of a list of $len(1)$, there would be done a single comparison checking if $l < r$, which is false, returning the original list.
Checking with our statement that mergesort uses $2^k(k+1)$ comparisons:
$$2^0(0+1)=1(1)=1$$
which means that our basis step holds.
**Inductive Step:** For our inductive step, we must prove that $P(k+1)$ holds, based on the assumptions that merge uses $a+b-1$ comparisons and that $P(k)$ is true. 
During the inductive step it is important to remember that $\dfrac{1}{2}2^{k+1}=2^k$ i.e. $2^k+2^k=2^{k+1}$.
Because mergesort splits up the list into to halves and performs mergesort on these, our inductive step basically says that 
$2^{k+1} \rightarrow L_1=2^k \text{ and } L_2=2^k$, which we each know to use $2^k(k+1)$ comparisons based on our inductive hypothesis. After running mergesort on the two halves, merge is run with them as inputs i.e. $Merge(2^k, 2^k)=2^k+2^k-1$. 

The proof is done using standard mathematical induction, starting with a base case of $k=0$. 
2. **Use induction to show that Mergesort uses less or equal to $2n log2 (n)$ comparisons for all $n \geq 2$ using the same assumptions regarding the Merge procedure as before.**
   Hints: A list with $n + 1$ elements is divided into two lists with $\left \lceil \dfrac{n+1}{2} \right \rceil$ and $\left \lfloor \dfrac{n+1}{2} \right \rfloor$ elements respectively by Mergesort. Furthermore the following in-/equalities might be useful:
$$
\begin{align} 
& 2 \left\lfloor \frac{n+1}{2} \right\rfloor \log_2\left(\left\lfloor \frac{n+1}{2} \right\rfloor\right) \leq 2 \left\lfloor \frac{n+1}{2} \right\rfloor \log_2\left(\left\lceil \frac{n+1}{2} \right\rceil\right), \\ 
& \left\lfloor \frac{n+1}{2} \right\rfloor + \left\lceil \frac{n+1}{2} \right\rceil = n+1, \\
& \left\lceil \frac{n+1}{2} \right\rceil \leq \frac{2}{3}(n+1) \quad \text{for } n \text{ a positive integer}, \\
& \log_2\left(\frac{2}{3}(n+1)\right) = \log_2(n+1) - \log_2\left(\frac{3}{2}\right), \\
& n + 1 - 2(n + 1) \log_2\left(\frac{3}{2}\right) < 0 \quad \text{for positive } n.
\end{align}
$$
**Basis Step:** We will use $P(1)$ for our basis step since the theory is set to hold for all $n \geq 2$ i.e. a list of $n=2^1=2 \rightarrow \{1,2\}$.
The aim is to show that mergesort uses less than or equal to $(2*2)\log_2(2)=4$ comparisons. We may assume that the Merge algorithm uses $a+b-1$ comparisons to combine lists with $a$ and $b$ elements.

With this list, we will call the mergesort algorithm with the parameters $L=\{1,2\}, \; l=0, \; r=1$, the following will happen with the number of comparisons being counted in the parentheses.
1. The if statement checks if $l<r$ (1). Since this is true, we will proceed with the procedure in the body of the if-statement.
2. The value of $m$ is set $m=\left\lfloor \dfrac{1+0}{2} \right \rfloor = 0$.
3. Mergesort is called with the values $L=\{1,2\}, \; l=0, \; r=0$, meaning that it only does a single comparison (2), checking if $l<r$, then returning because it is false.
4. Mergesort is called with the values $L=\{1,2\},\; l=1,\; r=1$, which only results in a single comparison (3), checking if $l<r$, then returning because it is false.
5. L is set to the return value of the Merge algorithm, which uses $1+1-1=1$ comparisons (4) (both halves of $L$ has a length of 1).
This shows that with a basis step of $P(1)$, the mergesort algorithm uses a total of 4 comparisons, which means that the theory holds. 

**Inductive Step:** For our inductive step we will show that $P(k+1)$ holds with the assumption that $P(k)$ holds for an arbitrary value $k$. The inductive step can be seen in subtask 1.

3. **What type of induction did you use? What does the result tell us about the complexity of Mergesort in big-O notation?**
The proof uses standard [[Induction#Mathematical Induction|mathematical induction]] starting with $P(1)$ as the basis step.
The fact that the algorithm uses $2n\log_2(n)$ tells us that the complexity of mergesort is within $O(n\log(n))$