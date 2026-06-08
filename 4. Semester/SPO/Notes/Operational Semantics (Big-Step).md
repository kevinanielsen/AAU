Operational semantics describes the sequence of elementary computations from the expression to its outcome (its value)

It operates directly over abstract syntax

There are two kinds of operational semantics
- “natural semantics” or “big steps”
$$e \twoheadrightarrow v$$
- “reduction semantics” or “small steps”
$$e \rightarrow e_1 \rightarrow e_2 \rightarrow \cdots \rightarrow v$$
## Value of a Variable
The value of a variable is given by an environment E (a function from variables to values)
$$E , e ↠ v$$
reads "in environment *E*, expression *e* has value *v*"
### Example
In environment $$E=\{a \mapsto 34,\; b \mapsto 55 \}$$
The expression $$a+b$$
Has value $$89$$
Which we write $$E,a+b \twoheadrightarrow 89$$
## Inference Rules
A relation may be defined as the smallest relation satisfying a set of rules with no premises (axioms) written
$$\frac{}{P}$$
and a set of rules with premises written
$$\frac{P_1 \quad P_2 \quad \dots \quad P_n}{P}$$
### Example
We can define the relation Even(n) with two rules
$$
\frac{}{\text{Even}(0)} \quad et \quad \frac{\text{Even}(n)}{\text{Even}(n+2)}
$$
that reads as follows
- on the one hand Even(0)
- on the other hand $\forall n$. $\text{Even}(n) \Rightarrow \text{Even}(n + 2)$.
The smallest relation satisfying these two properties coincide with the property $\{n \in \mathbb{N} \; |\; \exists m \in \mathbb{N}, n = 2m\}$, i.e. “n is an even natural number”:
- even natural numbers are included, by induction
- if odd numbers were included, we could remove the smallest
## Derivation Tree
A derivation is a tree whose internal nodes are rules with premises and whose leaves are axioms
### Example
$$
\dfrac{\dfrac{\dfrac{}{\text{Even}(0)}}{\text{Even}(2)}}{\text{Even}(4)}
$$
the set of derivations characterizes the smallest relation satisfying the inference rules.
## Modification of Variables
A statement may modify the value of some variables (through assignments).
To define the semantics of a statement s, we thus introduce the relation

$$E, s \twoheadrightarrow E'$$
that reads “in environment $E$, the evaluation of statement $s$ terminates
and leads to environment $E'$"

---
# Reading Big Step Semantics
## Example
$$ \frac{}{E, n \twoheadrightarrow n} \hspace{2cm} \frac{}{E, b \twoheadrightarrow b} $$
$$ \frac{x \in \text{dom}(E)}{E, x \twoheadrightarrow E(x)} $$
$$ \frac{E, e_1 \twoheadrightarrow n_1 \quad E, e_2 \twoheadrightarrow n_2 \quad n = n_1 + n_2}{E, e_1 + e_2 \twoheadrightarrow n} \quad \text{etc.} $$

### How to Read it
#### 1. Evaluating Numbers (Top Left)
$$\frac{}{E, n \twoheadrightarrow n}$$
* Plain English: In any environment $E$, a literal number $n$ simply evaluates to itself.
* Concept: The number `5` is just `5`. You don't need any prior steps or calculations to figure out what a raw number means. Because the top is empty, this is an axiom.

#### 2. Evaluating Booleans (Top Right)
$$\frac{}{E, b \twoheadrightarrow b}$$
* Plain English: In any environment $E$, a boolean value $b$ evaluates to itself.
* Concept: Just like numbers, a literal `true` or `false` requires no calculation. It just is what it is.

#### 3. Evaluating Variables (Middle)
$$\frac{x \in \text{dom}(E)}{E, x \twoheadrightarrow E(x)}$$
* Plain English: If a variable $x$ exists in the domain (the list of known variables) of your environment $E$, then $x$ evaluates to the value stored for it in $E$.
* Concept: If your program encounters the variable `x`, it looks it up in memory. If memory says `x = 10`, then `x` evaluates to `10`.

#### 4. Evaluating Addition (Bottom)
$$\frac{E, e_1 \twoheadrightarrow n_1 \quad E, e_2 \twoheadrightarrow n_2 \quad n = n_1 + n_2}{E, e_1 + e_2 \twoheadrightarrow n}$$
* Plain English: To evaluate an addition expression, three things must happen first:
	1.  The first part of the expression ($e_1$) evaluates to a number ($n_1$).
	2.  The second part of the expression ($e_2$) evaluates to a number ($n_2$).
	3.  You perform standard mathematical addition to get a final number $(n = n_1 + n_2)$.
* Conclusion: If those three premises are met, then the entire expression $e_1 + e_2$ evaluates to that final sum $n$.
* Concept: To calculate `(5 * 2) + 4`, you first have to evaluate the left side (`10`), evaluate the right side (`4`), and then mathematically add them together (`14`).
### Example
With $E=\{a \mapsto 34, \; b \mapsto 55\}$, we have
$$
\dfrac{\dfrac{a\in \text{dom}(E)}{E,a \twoheadrightarrow 34}\quad \dfrac{b \in \text{dom}(E)}{E,b \twoheadrightarrow 55}\quad 89=34+55}{E, a+b \twoheadrightarrow 89}
$$