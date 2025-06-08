**Literature:** [Rosen], Sections 7.3 + slides
Bayes' Theorem is used for finding the probability that a particular event occurs on the basis of partial evidence.
# Bayes' Theorem
Suppose we know the probability that an even $F$ occurs, $p(F)$, but we have knowledge that an event $E$ occurs. Then the conditional probability that $F$ occurs given that $E$ occurs, $p(F \vert E)$, is a more realistic estimate than $p(F)$. 
## Example
![[bayes_theorem_boxes_example.png]]
We have two boxes. The first contains two green balls and seven red balls; the second contains four green balls and three red balls. Bob selects a ball by first choosing one of the two boxes at random. He then selects one of the balls in this box at random. If Bob has selected a red ball, what is the probability that he selected a ball from the first box?

### Solution
- $E$ is the event that Bob chose a red ball
- $\overline E$ is the event that Bob chose a green ball
- $F$ is the event that Bob chose from the first box
- $\overline F$ is the event that Bob chose from the second box
We want to find $p(F|E)$, i.e., that the ball bob selected came from the first box, given it was red.
By the definition of conditional probability, we have $p(F|E)=p(F \cap E)/p(E)$.

- The first box contains 7 red balls out of a total of nine balls, we know that $p(E|F)=7/9$, i.e. the probability of picking a red ball given that you pick from the first is 7/9.
- The second box contains 3 red balls out of a total of 7 balls, i.e., $p(E|\overline F)=3/7$. 
- We assume that Bob selects a box at random so $p(F)=p(\overline F)=1/2$.

Because $p(E|F)=p(E \cap F)/p(F)$, it follows that $p(E \cap F)=p(E|F)p(F)=\frac79 \cdot \frac12 = \frac{7}{18}$.

Because $p(E|\overline F)=p(E \cap \overline F)/p(\overline F)$, it follows that $p(E \cap \overline F)=p(E | \overline F)p(\overline F)=\frac37 \cdot \frac12 = \frac3{14}$.

Now we can find $p(E)$. Note that $E=(E \cap F) \cup (E \cap \overline F)$, where $E \cap F$ and $E \cap \overline F$ are disjoint sets.

It follows that 
$$
p(E)=p(E \cap F)+p(E \cap \overline F)=\frac7{18}+\frac3{14}=\frac{49}{126}+\frac{27}{126}=\frac{76}{126}=\frac{38}{63}.
$$
Now, we have $p(F \cap E)=7/18$ and $p(E)=38/63$, we can conclude that
$$
p(F | E) = \frac{p(F \cap E)}{P(E)}=\frac{7/18}{38/63}=\frac{49}{76}\approx 0.645
$$

> [!NOTE] Bayes' Theorem
> Suppose that $E$ and $F$ are events from a sample space $S$ such that $p(E) \ne 0$ and $p(F) \ne 0$. Then
> $$p(F|E)=\frac{p(E|F)p(F)}{p(E|F)p(F)+p(E|\overline F)p(\overline F)}.$$

## Generalized Bayes' Theorem
Suppose that $E$ is an event from a sample space $S$ and that $F_1, F_2, \dots, F_n$ are mutually exclusive events such that $\bigcup_{i=1}^n F_i=S$. Assume that $p(E) \ne 0$ and $p(F_i) \ne 0$ for $i=1,2,\dots,n$. Then
$$
p(F_j | E)=\frac{p(E|F_j)p(F_j)}{\sum_{i=1}^np(E|F_i)p(F_i)}
$$
