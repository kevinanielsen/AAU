Q16
$$
\dfrac{\Gamma \vdash x : \texttt{int}}{\Gamma \vdash \lambda x.42 : \texttt{int} \to \texttt{int}}
$$
Q17
$$λx.λy.x(y): (int \to int) \to int$$
$$λy.λx.x(y):(int \to int) \to int$$
Q18
$$\dfrac{\Gamma \vdash e_1 : \texttt{bool} \quad \Gamma \vdash e_2 : \tau \quad \Gamma \vdash e_3 : \tau}{\Gamma \vdash \texttt{if $e_1$ then $e_2$ else $e_3:\tau$}}$$
Q19
$$\dfrac{\Gamma \vdash e_1:(\tau_1 \to \tau_2) \quad \Gamma \vdash e_2 : \tau_1}{\Gamma \vdash e_1(e_2):\tau_2}$$
Q20
$$
\dfrac{\Gamma, x:\tau_1 \vdash e:\tau_2}{\Gamma \vdash \lambda x.e: \tau_1 \to \tau_2}
$$
$$
\dfrac{\Gamma \vdash e_1:\tau_1 \quad \Gamma, x:\tau_1 \vdash e_2:\tau_2}{\Gamma \vdash \texttt{let $x = e_1$ in $e_2:\tau_2$}}
$$
Q21
The short answer is: No, $\delta = \lambda x.x(x)$ is not well-typed. Here is exactly how to break down the answer for your exam.
### Part 1: Why is $\delta$ ill-typed?
1. **$x$ is a function:** Because $x$ is being called, it must have a function type: $\tau_1 \to \tau_2$.
2. **$x$ is the argument:** The argument being passed to $x$ is also $x$. Therefore, the expected input type ($\tau_1$) must exactly match the overall type of $x$.
3. **The Paradox:** If we substitute $x$'s type ($\tau_1 \to \tau_2$) into its own input requirement ($\tau_1$), we get the equation:   
$$\tau_1 = \tau_1 \to \tau_2$$
This creates an **infinite type**. If you try to resolve it, you get $(\dots \to \tau_2) \to \tau_2 \to \tau_2$. Because our type system only allows finite, concrete types (like $\texttt{int}$, $\texttt{bool}$, or a fixed function signature), it is mathematically impossible to assign a valid type to $x$. The type-checker will reject it (this specific failure is often called failing the "occurs check").
### Part 2: What does this mean for $\Omega$ from Q15?
In Question 15, $\Omega$ is defined as $(\lambda x.x(x))(\lambda x.x(x))$.

If you try to evaluate $\Omega$, it passes the second function into the first, which just replicates the exact same expression endlessly. It is an infinite loop!

Because $\Omega$ relies entirely on the $\lambda x.x(x)$ structure (which we just proved is rejected by the type checker), $\Omega$ is also completely rejected by the type system. It will fail to compile.
### Part 3: What can we conclude about the type system?
Because the type system rejects $\Omega$ and $\delta$, you can conclude a very powerful property about this language: It guarantees termination.

In computer science, this is called Strong Normalization. Because you cannot assign a valid type to self-applying functions, it is impossible to write an infinite loop in this statically typed language. Every well-typed program is guaranteed to eventually halt and return a value.

The trade-off is that the type system is _restrictive_. It rejects some programs (like loops or recursion) that might be useful, forcing you to add specific built-in language features (like the `let rec` in Question 24) if you actually want to allow recursive loops.