# Insertion Sort
Imagine a mixed deck of cards and an empty hand, you pick up a card, one at a time, and insert it at the correct place in your hand. 

Runtime is $O(n^2)$

[[insertion_sort_pseudo.png|Insertion Sort Pseudo Code]]

Effective for:
- Small values of n
- Almost sorted sequences
# Merge Sort
Recursive divide and conquer algorithm. 
1. It splits the sequence down the middle.
2. Calls the algorithm recursively. When it receives a sequence with only one element, it returns the trivially sorted element. 
3. It combines the two sorted sub-sequences in a sorted fashion. 

Runtime is $\Theta(n\log n)$

[[merge_sort_pseudo.png|Merge Sort Pseudo Code]]
[[merge_pseudo.png|Merge Pseudo Code]]
# Quicksort
Recursive divide and conquer algorithm. It has a smaller space complexity than merge sort, and the implementation is more simple. 
1. It picks a pivot element $p$ and splits it up into two parts, one where everything is lower than $p$ and one where everything is higher than or equal to $p$. 
2. It calls Quicksort recursively on the two parts.

The performance of Quicksort is dependent on the input. The worst case is that every recursive call makes a single new sub-problem of size $n-1$ this leads to a runtime of $\Theta(n^2)$. 
The best case is that each recursive call makes 2 new sub-problems of size $n/2$ this leads to a runtime of $\Theta(n \log n)$. 
The average case is that the recursive calls fluctuate between "good" and "bad" splits, which will result in a runtime of $\Theta (n \log n)$.

We can avoid getting the worst case by randomizing the the partition.

[[quicksort_pseudo.png|Quicksort Pseudo Code]]
[[partition_pseudo.png|Partition Pseudo Code]]
[[randomized_partition_pseudo.png|Randomized Partition Pseudo Code]]
