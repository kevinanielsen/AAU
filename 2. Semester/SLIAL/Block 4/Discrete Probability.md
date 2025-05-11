The probability of an event can be described as the number of successful outcomes divided by the number of possibly outcomes. This description holds when there are finitely many, equally likely, outcomes.

An experiment is a procedure that yields one of a given set of possible outcomes. The sample space of the experiment is the set of possible outcomes. An event is a subset of the sample space.

If $S$ is a finite nonempty sample space of equally likely outcomes, and $E$ is an event, that is, a subset of $S$, then the *probability* of $E$ is $p(E)=\dfrac{\vert E \vert}{\vert S \vert}$.

In this (Laplace's) definition, the probability of an event is between 0 and 1. Note that if $E$ is an event from a finite sample space $S$, then $0 \leq \vert E \vert \leq \vert S \vert$, because $E \subseteq S$. Thus, $0 \leq p(E)=\vert E \vert / \vert S \vert \leq 1$.
# Theorems
## Theorem 1
Let $E$ be an event in a sample space $S$. The probability of the event $\bar E = S - E$, the complementary event of $E$ is given by
$$p(\bar E) = 1-p(E).$$
## Theorem 2
Let $E_1$ and $E_2$ be events in the sample space $S$. Then
$$
p(E_1 \cup E_2)=p(E_1)+p(E_2)-p(E_1 \cap E_2).
$$
### Example
Let’s consider a standard deck of 52 playing cards.

- Let event $E_1$: drawing a **heart** (13 cards).
- Let event $E_2$: drawing a **king** (4 cards).

We want to compute the probability of drawing a **heart or a king**, i.e., $P(E_1 \cup E_2)$.

From the deck:

- $P(E_1) = \frac{13}{52}$
- $P(E_2) = \frac{4}{52}$
- $P(E_1 \cap E_2) = \frac{1}{52}$ (only the king of hearts)

Using the formula:

$$
P(E_1 \cup E_2) = P(E_1) + P(E_2) - P(E_1 \cap E_2)
$$

Substitute the values:

$$
P(E_1 \cup E_2) = \frac{13}{52} + \frac{4}{52} - \frac{1}{52} = \frac{16}{52} = \frac{4}{13}
$$

So, the probability of drawing **either** a heart or a king is $\frac{4}{13}$. The "either" is important because if we draw a king of hearts, then that would be **both** a king and a heart, which is why we subtract the probability of that happening.
