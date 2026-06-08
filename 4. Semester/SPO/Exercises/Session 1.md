## Question 1
$$
\dfrac{}{E, (v_1, v_2) \twoheadrightarrow (v_1, v_2)}
$$
$$
\dfrac{E, e \twoheadrightarrow (v_1, v_2)}{E, \verb|fst| \; e \twoheadrightarrow v_1} \quad \dfrac{E, e \twoheadrightarrow (v_1, v_2)}{E, \verb|snd| \; e \twoheadrightarrow v_2}
$$
## Question 2
$$ 
\dfrac{
  \dfrac{E, x \twoheadrightarrow 1 \quad E, 0 \twoheadrightarrow 0 \quad 1 > 0}{E, x > 0 \twoheadrightarrow \text{true}} 
  \quad
  \dfrac{
    \dfrac{E, x \twoheadrightarrow 1 \quad E, 1 \twoheadrightarrow 1 \quad 0 = 1 - 1}{E, x - 1 \twoheadrightarrow 0}
  }{E, x := x - 1 \twoheadrightarrow E_1} 
  \quad
  \dfrac{E_1, x > 0 \twoheadrightarrow \text{false}}{E_1, \text{while } x > 0 \text{ do } x := x - 1 \twoheadrightarrow E_1}
}{E, \text{while } x > 0 \text{ do } x := x - 1 \twoheadrightarrow E_1} 
$$
## Question 4
```
i := 0;
p := 0;
while i < 5 do {
p := (i + 1, p);
i := i + 1;
};
print(p)
```

p: (1, 0); i: 1
p: (2, (1, 0)); i: 2
p: (3, (2, (1, 0))); i: 3
p: (4, (3, (2, (1, 0)))); i: 4
p: (5, (4, (3, (2, (1, 0))))); i: 5
## Question 5
$$
\dfrac{E, s \twoheadrightarrow E_1 \quad E_1, e \twoheadrightarrow \;\verb|false|\; \quad E_1, \;\verb|repeat|\; s \;\verb|until|\; e \twoheadrightarrow E_2}{E, \verb|repeate|\; s \;\verb|until|\; e \twoheadrightarrow E_2}
$$
$$
\dfrac{ E, s\twoheadrightarrow E_1 \quad E_1, e \twoheadrightarrow \;\verb|true|\;}{E, \verb|repeate|\; s \;\verb|until|\; e \twoheadrightarrow E_1}
$$
## Question 7 (From Gemini)
Based on the description provided in Question 7 and the formal big-step semantics style from your reference image, we need two inference rules to define the behavior of the `for` loop: one for the base case (when the loop terminates) and one for the recursive step (when the loop body executes).

Here are the inference rules that capture that exact description:

### 1. Loop Termination (Base Case)

When the evaluated starting value ($n_1$) is strictly greater than the evaluated ending value ($n_2$), the loop does not execute, and the environment remains unchanged ($E$).

$$\frac{E, e_1 \rightarrow n_1 \quad E, e_2 \rightarrow n_2 \quad n_1 > n_2}{E, \text{\texttt{for }} i = e_1 \text{\texttt{ to }} e_2 \text{\texttt{ do }} s \rightarrow E}$$

### 2. Loop Execution (Recursive Case)

When $n_1 \leq n_2$, the loop body $s$ is evaluated in the environment updated with the loop counter $E\{i \mapsto n_1\}$. This yields a new environment $E'$. We then recursively execute the rest of the loop from $n_1 + 1$ to $n_2$ in that new environment $E'$, which eventually yields the final environment $E''$.

$$\frac{E, e_1 \rightarrow n_1 \quad E, e_2 \rightarrow n_2 \quad n_1 \leq n_2 \quad E\{i \mapsto n_1\}, s \rightarrow E' \quad E', \text{\texttt{for }} i = n_1 + 1 \text{\texttt{ to }} n_2 \text{\texttt{ do }} s \rightarrow E''}{E, \text{\texttt{for }} i = e_1 \text{\texttt{ to }} e_2 \text{\texttt{ do }} s \rightarrow E''}$$

**Note on Evaluation:** By explicitly using $n_2$ as the upper bound in the recursive step (as dictated by the text: `for` $i = n_1 + 1$ `to` $n_2$), the semantics ensure that the upper bound expression $e_2$ is only evaluated once at the very beginning, rather than being re-evaluated on every single iteration.