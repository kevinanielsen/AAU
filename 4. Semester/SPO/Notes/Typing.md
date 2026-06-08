We introduce **types**, with the following abstract syntax
$$
\begin{array}{rrl}
\tau &::= &&\textbf{type} \\
&| &\text{int} &\text{type of integer values} \\
&| &\text{bool} &\text{type of Boolean values}
\end{array}
$$
- the type of a variable is given by a typing environment $\Gamma$ (a function from variables to types)
- the typing judgment is written

$$\Gamma  \vdash e : \tau$$
- and reads “in typing environment $\Gamma$, expression $e$ has type $\tau$”
- we use inference rules to define $\Gamma \vdash e : \tau$.
## Examples of Typing Expressions
$$
\dfrac{}{\Gamma \vdash n : int} \quad \dfrac{}{\Gamma \vdash b : bool}
$$
$$\dfrac{x \in \text{dom}(\Gamma)}{\Gamma \vdash x : \Gamma (x)}$$
$$\dfrac{\Gamma \vdash e_1 : int \quad \Gamma \vdash e_2 : int}{\Gamma \vdash e_1 + e_2 : int}$$
$$\dfrac{\Gamma \vdash e_1 : int \quad \Gamma \vdash e_2 : int}{\Gamma \vdash e_1 < e_2 : bool}$$
# Type Checking Statements
to type statements, we introduce a new judgment
$$\Gamma \vdash s$$
that reads “in environment $\Gamma$, statement $s$ is well-typed”
## Examples
$$\dfrac{}{\Gamma \vdash \text{skip}} \quad \dfrac{\Gamma \vdash s_1 \quad \Gamma \vdash s_2}{\Gamma \vdash s_1 ; s_2}$$
$$\dfrac{\Gamma \vdash x : \tau \quad \Gamma \vdash e: \tau}{\Gamma \vdash x \leftarrow e}$$
$$\dfrac{\Gamma \vdash e : bool \quad \Gamma \vdash s_1 \quad \Gamma \vdash s_2}{\Gamma \vdash \text{if } e \text{ then } s_1 \text{ else } s_2}$$
$$\dfrac{\Gamma \vdash e : \text{bool} \quad \Gamma \vdash s}{\Gamma \vdash \text{while } e \text{ do } s}$$
# Subtypes
we say that a type $\tau_1$ is a subtype of a type $\tau_2$, which we write
$$\tau_1 \leq \tau_2$$
if any value with type $\tau_1$ can be considered as a value with type $\tau_2$.

In an object-oriented language, inheritance induces subtyping:
if a class $\texttt{B}$ inherits from a class $\texttt A$, we have
$$\texttt B \le \texttt A$$
i.e. any value of type $\texttt B$ can be seen as a value of type $\texttt A$.
# Typing Judgement
the typing judgment that we are going to define is written
$$\Gamma \vdash e : \tau$$
and is read “ in the environment $\Gamma$, the expression $e$ has type $\tau$”
the environment $\Gamma$ associates a type $\Gamma(x)$ with every variable $x$ that is free in $e$.
![[typing_rules.png]]
$\Gamma + x : \tau$ is the environment $\Gamma'$ defined by
$\Gamma'(x) = \tau$ and $\Gamma'(y) = \Gamma(y)$ otherwise
$$\begin{array}{ccccc} \tau_1: & (\alpha & \times & \beta) & \to & \text{int} \\ & \downarrow && \downarrow && \downarrow \\ \tau_2: & (\text{int} & \times & \text{bool}) & \to & \gamma \end{array}$$