# Exercise 1.
i) 
$$
\begin{aligned}
s   &= [x \mapsto 3, y \mapsto 5] \\
s_1 &= [x \mapsto 2, y \mapsto 5] \\
s_2 &= [x \mapsto 2, y \mapsto 3] \\
\end{aligned}
$$

$$
\dfrac{
    \dfrac{s \vdash 2 \to_A 2}{\langle \text{x} := 2, s \rangle \to s_1} 
    \quad 
    \dfrac{
        \dfrac{}{\langle \text{skip}, s_1 \rangle \to s_1} 
        \quad 
        \dfrac{s_1 \vdash 3 \to_A 3}{\langle \text{y} := 3, s_1 \rangle \to s_2}
    }{\langle \text{skip}; \text{y} := 3, s_1 \rangle \to s_2}
}{\langle \text{x} := 2; (\text{skip}; \text{y} := 3), s \rangle \to s_2}
$$
ii)
$$
\begin{aligned}
s&= [x \mapsto 2, y \mapsto 3, z \mapsto 5] \\
S&=(\text{if $x+1<y$ then $z:=2$ else $z:=3$})
\end{aligned}
$$
$$
\dfrac{\dfrac{s \vdash 5 \to_A 5}
{\langle z:=5, s \rangle \to s}}
{\langle \text{if $x<y$ then $z:=5$ else }S, s \rangle \to s}
$$
iii)
Let $S = \text{x} := \text{x} + 1; \text{y} := 2$
Let $W = \text{while x} \le 5 \text{ do } S$

$$
\begin{aligned}
\sigma &= [x \mapsto 2, y \mapsto 0] \\
\sigma_1 &= [x \mapsto 3, y \mapsto 0] \quad \text{(after } x:=3 \text{)} \\
\sigma_{2a} &= [x \mapsto 4, y \mapsto 0] \quad \text{(iter 1: after } x:=x+1 \text{)} \\
\sigma_2 &= [x \mapsto 4, y \mapsto 2] \quad \text{(iter 1: after } y:=2 \text{)} \\
\sigma_{3a} &= [x \mapsto 5, y \mapsto 2] \quad \text{(iter 2: after } x:=x+1 \text{)} \\
\sigma_3 &= [x \mapsto 5, y \mapsto 2] \quad \text{(iter 2: after } y:=2 \text{)} \\
\sigma_{4a} &= [x \mapsto 6, y \mapsto 2] \quad \text{(iter 3: after } x:=x+1 \text{)} \\
\sigma_4 &= [x \mapsto 6, y \mapsto 2] \quad \text{(iter 3: after } y:=2 \text{)}
\end{aligned}
$$

### 2. Main Composition Tree
$$
\dfrac{
    \dfrac{}{\langle \text{skip}, \sigma \rangle \to \sigma}
    \quad
    \dfrac{
        \dfrac{\sigma \vdash 3 \to_A 3}{\langle \text{x} := 3, \sigma \rangle \to \sigma_1}
        \quad
        \dfrac{\vdots \text{ (See Tree } W \text{ below)}}{\langle W, \sigma_1 \rangle \to \sigma_4}
    }{\langle \text{x} := 3; W, \sigma \rangle \to \sigma_4}
}{\langle \text{skip}; \text{x} := 3; W, \sigma \rangle \to \sigma_4}
$$

### 3. While Loop Evaluation ($W$)

**Iteration 1 (from $\sigma_1$):**
$$
\dfrac{
    \sigma_1 \vdash x \le 5 \to_B \text{T}
    \quad
    \dfrac{
        \dfrac{\sigma_1 \vdash x + 1 \to_A 4}{\langle \text{x} := \text{x} + 1, \sigma_1 \rangle \to \sigma_{2a}}
        \quad
        \dfrac{\sigma_{2a} \vdash 2 \to_A 2}{\langle \text{y} := 2, \sigma_{2a} \rangle \to \sigma_2}
    }{\langle S, \sigma_1 \rangle \to \sigma_2}
    \quad
    \dfrac{\vdots \text{ (Iter 2)}}{\langle W, \sigma_2 \rangle \to \sigma_4}
}{\langle W, \sigma_1 \rangle \to \sigma_4}
$$

**Iteration 2 (from $\sigma_2$):**
$$
\dfrac{
    \sigma_2 \vdash x \le 5 \to_B \text{T}
    \quad
    \dfrac{
        \dfrac{\sigma_2 \vdash x + 1 \to_A 5}{\langle \text{x} := \text{x} + 1, \sigma_2 \rangle \to \sigma_{3a}}
        \quad
        \dfrac{\sigma_{3a} \vdash 2 \to_A 2}{\langle \text{y} := 2, \sigma_{3a} \rangle \to \sigma_3}
    }{\langle S, \sigma_2 \rangle \to \sigma_3}
    \quad
    \dfrac{\vdots \text{ (Iter 3)}}{\langle W, \sigma_3 \rangle \to \sigma_4}
}{\langle W, \sigma_2 \rangle \to \sigma_4}
$$

**Iteration 3 (from $\sigma_3$):**
$$
\dfrac{
    \sigma_3 \vdash x \le 5 \to_B \text{T}
    \quad
    \dfrac{
        \dfrac{\sigma_3 \vdash x + 1 \to_A 6}{\langle \text{x} := \text{x} + 1, \sigma_3 \rangle \to \sigma_{4a}}
        \quad
        \dfrac{\sigma_{4a} \vdash 2 \to_A 2}{\langle \text{y} := 2, \sigma_{4a} \rangle \to \sigma_4}
    }{\langle S, \sigma_3 \rangle \to \sigma_4}
    \quad
    \dfrac{\vdots \text{ (Termination)}}{\langle W, \sigma_4 \rangle \to \sigma_4}
}{\langle W, \sigma_3 \rangle \to \sigma_4}
$$

**Loop Termination (from $\sigma_4$):**
$$
\dfrac{
    \sigma_4 \vdash x \le 5 \to_B \bot
}{\langle W, \sigma_4 \rangle \to \sigma_4}
$$
# Exercise 2.
## i)
Let the state be $s$.
Let $b \equiv \neg(2 < (1 + 1))$
Let $S_{body} \equiv \text{if } x < x \text{ then } x := 2 \text{ else skip}$
Thus, the original statement is $S \equiv \text{while } b \text{ do } S_{body}$.

We trace the small-step evaluation of $\langle S, s \rangle$:

$$\langle S, s \rangle$$

**1. Unfold the While loop (While Rule):**
$$\rightarrow \langle \text{if } b \text{ then } (S_{body}; S) \text{ else skip}, s \rangle$$

**2. Evaluate the boolean condition $b$:**
$$\langle 1+1, s \rangle \rightarrow \langle 2, s \rangle$$
$$\langle 2<2, s \rangle \rightarrow \langle \text{false}, s \rangle$$
$$\langle \neg\text{false}, s \rangle \rightarrow \langle \text{true}, s \rangle$$
This gives us:
$$\rightarrow^* \langle \text{if true then } (S_{body}; S) \text{ else skip}, s \rangle$$

**3. Evaluate the If statement (If-True Rule):**
$$\rightarrow \langle S_{body}; S, s \rangle$$
Substituting $S_{body}$ back in:
$$= \langle (\text{if } x < x \text{ then } x := 2 \text{ else skip}); S, s \rangle$$

**4. Evaluate $S_{body}$:**
For any value $v$ of $x$ in state $s$, $\langle x < x, s \rangle \rightarrow^* \langle \text{false}, s \rangle$.
Therefore, applying the **If-False Rule**:
$$\rightarrow^* \langle \text{skip}; S, s \rangle$$

**5. Evaluate the sequence (Sequence/Skip Rule):**
$$\rightarrow \langle S, s \rangle$$

**Conclusion:**
We have shown that $\langle S, s \rangle \rightarrow^+ \langle S, s \rangle$. Because the execution returns to its exact initial configuration in a finite number of valid transitions, the statement will loop forever. $\blacksquare$
## ii)
