# 1's Complement
All ‘0’s become ‘1’s
All ‘1’s become ‘0’s
## Example 
$$\begin{aligned}&(10110000)_2\\ \Rightarrow &(01001111)_2\end{aligned}$$
# 2's Complement
To find the 2's complement of a number (which is how you make it negative), you just follow two steps:
1. **Flip the bits (1's Complement):** Turn every `0` into a `1`, and every `1` into a `0`.
2. **Add 1:** Add a single `1` to the result.
Alternatively, toggle all bits to the left of the first '1' from the right $(10110000)_2 \Rightarrow (01010000)_2$.
## Example
$$
\begin{aligned}
&(10110000)_2 \\
\text{1's complement}\Rightarrow &(01001111)_2 \\
\text{2's complement} \Rightarrow &(01010000)_2
\end{aligned}
$$
# Binary Subtraction Using 2's Complement
![[binary subtraction using 2s complement.png]]
# Signed and Unsigned Numbers
![[signed and unsigned numbers binary.png]]