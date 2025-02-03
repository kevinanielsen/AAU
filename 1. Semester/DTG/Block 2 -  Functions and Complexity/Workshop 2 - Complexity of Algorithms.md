A search function takes as inputs a list $(a_0, \ldots, a_{n−1})$ and an element $x$. The task is to find the element $x$ in the list if it is a member. More precisely, if there is an index $i$ such that $a_i = x$ then a search algorithm should return the index $i$. If there is no such index we want a return value of $−1$. We will restrict ourselves to lists of integers. If we denote by $A$ the set of all finite lists of integers then a search function is a map 
$$ 
\begin{align}
f: A \times \mathbb{Z} &\rightarrow \mathbb{Z}_{\geq-1} \\
f((a_0, \ldots, a_{n-1}),x) &= \begin{cases} i & \text{if } a_i = x \\ -1 & \text{otherwise.} \end{cases}
\end{align}
$$
# Exercise 1
## a) Explain why $f$ is not a function using the list $(3, 4, 4, 5)$ as an example.
A function can only have one image for every preimage and in this case, the preimage 4 could result in either index 2 or 3 as the images. I.e. the function $f$ fails to define a unique output when repeated elements occur in the input list.

## b) If we require the lists we use to not have repeated elements, then $f$ can be seen as a function. Decide whether this function is injective, surjective or bijective.
Since every element in the input list would result in a different output, then the function would be seen as a one-to-one (injective).

Furthermore, if we run the function looking for each element in the list, we would get every element from the domain i.e. no element in the codomain is unmapped, therefore the function is also onto (surjective). This is only the case, however, if the domain also includes an element not in the input list, thereby also mapping the $-1$ in the codomain.

With the function being both surjective and injective, the function is classified as bijective. 
# Exercise 3
We will now study the theoretical complexity of the two algorithms. We will count comparisons made in the course of the algorithm.
## a) Argue that the linear search algorithm will use $2n + 2$ comparisons in the worst case. Describe the inputs for which this will happen.
The worst case for linear search is that the search element is not in the input list. The algorithm will do 2 comparisons for each element in the list, this is the $2n$. The last 2 comparisons are still done when end of the list is reached, checking one last time, if the element is the right one and if the end of the list is reached i.e. $i < n$. 

This could happen with an input list of $(1,2,3,4)$ and an $x$ (search element) of 5. 
## b) Show that the number of comparisons in the worst case for linear search is in $\Theta(n)$.
As we discussed in question a) above, the worst case would result in $2n+2$ comparisons. We know that when discussing time complexity, two witnesses are used $C, k$, where $C$ is the constant we multiply the growth with. This means that the growth $n$ i.e. the complexity $\Theta (n)$ would cover the $2n+2$ since we could set the value of $C$ to be 3 and the number of comparisons would be within that limit.
## c) Consider the binary search algorithm and assume that the list has length $n = 2^k$.
### i) Check that every full iteration of the while loop uses two comparisons.
The while loop does exactly two comparisons each iteration:
1. Checking if $i<j$.
2. Checking if $x>a_m$
### ii) Show that in the first iteration of the while loop $m = 2^{k−1}−1$.
$$ 
\begin{align}
i &= 0 \\
j &= 2^k-1 \\
m &= \left\lfloor \frac{0+(2^k-1)}{2} \right\rfloor = \left\lfloor \frac{2^k-1}{2} \right\rfloor = 2^{k-1}-1
\end{align}
$$
### iii) Argue that after the first time the while loop has run we have excluded half the elements of the list.
We use the $m$ variable to get the median value (lower-middle value if $n$ is even) of the list. Each iteration of the while loop, we check if $x>a_m$ i.e. if the search value is higher than the middle value, if so, we set $i = m + 1$, else we set $j = m$ $i, j$ being the values we use to find the middle-most value. Thereby, we exclude half of the values in the list every iteration.
### iv) Check that we have to half the list $log_2(n)$ times to end up with a list of just one element. (Remember that we assume $n = 2^k$. What happens if $n$ is not a power of 2?)

Since $n$ is a power of 2, we know that every time we half the list, it is like removing a power from the 2. E.g. if we start off with $2^4$, when we half the list we have $2^3$.  

$log_a(n)$ is used to find the power $a$ has to have to reach the value $n$. We also know that any number, thereby also 2, lifted to a power of 0, equals 1. 
Therefore, halving the list $log_2(n)$ times would result in a singular element.
### v) Consider the final steps of the algorithm. Once $i = j$ the while loop checks its run condition once more. Then the algorithm continues to check if we have found the element in question. Show that the algorithm will need $2 log_2(n) + 2$ comparisons.
We know that to end up with a singular element, we need to half the list $log_2(n)$ times. Since the algorithm halves the list at every iteration, the algorithm needs to run $log_2(n)$ times. 

We also know that the algorithm uses 2 comparisons at every iteration of the while loop, this results in $2*log_2(n)$ comparisons. 

Lastly, when only a singular element left, the algorithm will do a check if $i < j$ and if this is not the case, it checks if $x=a_i$ i.e. if the last element is the list is correct. These being the last two comparisons, resulting in a total of $2log2(n)+2$ comparisons.
## d) Show that the number of comparisons needed for binary search is $\Theta(log_2(n))$.
As explained in question c.v, the algorithm will need a total of $2log_2(n)+2$ operations. This number is the same regardless of the order of the list, since binary search is always used with ordered list inputs. This means that the worst- average and best case are always the same. Therefore, we use $\Theta$ to represent the complexity of the algorithm. 

As previously discussed, we use the witnesses $C,k$ when discussing complexity. This means that $\Theta (log_2(n))$ with a high enough value for $C$ will cover the number of comparisons i.e. the growth of the function.
## ~~e) Compare these theoretical results with the results you got from your implementation.~~

## f) Assume we have a list of 10000 elements and need to search for several elements in it. We want to figure out when it pays oﬀ to sort the list before searching. Use the $\Theta$ approximations for the following exercises when calculating the number of comparisons made, i.e., assume linear search uses n comparisons and binary search uses $log_2(n)$ comparisons.
### i) How many comparisons will be used when we search for $m$ elements using linear search?
Linear search requires $\Theta(n)$ comparisons for each search If $m$ elements are searched, then the total number of comparisons is $m*\Theta(n) = \Theta(mn)$. 
### ii) We will see that a list of $n$ elements can be sorted with an eﬀort of $\Theta(n log_2(n))$. How many operations are needed if we sort the list first, then search for $m$ elements using binary search?
For this question, the theory of the sum of functions will be used.
We know that binary search has a complexity of $\Theta(log_2(n))$ and sorting the list has a complexity of $\Theta (nlog_2(n))$. Therefore sorting the list first will use $log_2(n)+nlog_2(n)$ operations. 
### iii) At which point, i.e., for which $m$, do these two approaches have similar complexity? Which one is better when?
Figuring out at which point the two approaches have similar complexity can be done by using the method for finding the intersections of two functions, because as we know, the value for big-theta is a function. 
Linear search: $mn$
Binary search + sorting: $(m\log_2(n))+n\log_2(n)$
Intersection:
$$ 
\begin{align}
mn &= m\log_2(n)+n\log_2(n) \\
mn - m\log_2(n)&=n\log_2(n) \\
m(n-\log_2(n)) &=n\log_2(n) \\\\
m &= \dfrac{n\log_2(n)}{n-\log_2(n)}
\end{align}
$$
This means that 
$$
\begin{align} 
m < \dfrac{n\log_2(n)}{n-\log_2(n)} & \text{Linear search is better} \\\\
m > \dfrac{n\log_2(n)}{n-\log_2(n)} & \text{Sorting + binary search is better}
\end{align}
$$
Inserting the value of 10000 for $n$:

$m < 13,31$ Linear search is better, and $m > 13,31$ then sorting + binary search is better.