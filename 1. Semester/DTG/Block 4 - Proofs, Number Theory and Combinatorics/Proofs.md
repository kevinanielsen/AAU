> Proofs in mathematics are valid arguments that establish the truth of mathematical statements.

*Arguments* are sequences of statements that end with conclusions.

*Valid* meaning the conclusion or final statement of the argument, must follow from the truth of the preceding statements. 

*Fallacies* are forms of incorrect reasoning, which lead to invalid arguments.

The key to showing that an argument in propositional logic is valid is to show that its argument form is valid. 

A proof can use the hypothesis of the theorem, if any, axioms assumed to be true, and previously proven theorems. Using these ingredients and rules of inference, the final step of the proof establishes the truth of the statement being proved.

In practice, the proofs of theorems designed for human consumption are almost always *informal proofs*, where more than one rule of inference may be used in each step, where steps may be skipped, where the axioms being assumed and the rules of inference used are not explicitly stated. Informal proofs can often explain to humans why theorems are true, while computers are perfectly happy producing formal proofs using automated reasoning systems.

## 0.1 Terminology
### 0.1.1 Theorem
Formally, a theorem is a statement that can be shown to be true. In mathematical writing, the term theorem is usually reserved for a statement that is considered at least somewhat important. Other names include *facts* or *results*.
### 0.1.2 Axioms
Axioms (or *postulates*) are statements we assume to be true.
### 0.1.3 Lemma
A lemma (plural *lemmas* or *lemmata*) is a less important theorem which is helpful in the proof of other results. Complicated proofs are usually easier to understand when they are proved using a series of lemmas.
### 0.1.4 Corollary
A corollary is a theorem that can be established directly from a theorem that has been proved.
### 0.1.5 Conjecture
A conjecture is a statement that is being proposed to be a true statement, usually on the basis of some partial evidence, a heuristic argument, or the intuition of an expert. A proved conjecture becomes a theorem.

**Example of a valid argument in [[Logic#1 Propositional Logic|propositional logic]].**
"If you have a current password, then you can log onto the network."
"You have a current password."
Therefore,
"You can log onto the network."

If we consider $p$ the statement "You have a current password", and $q$ "You can log onto the network." Then, the argument has the form
$$
\begin{array}{l}
p \to q \\
p \\
\hline
\therefore q
\end{array}
$$
We know that when $p$ and $q$ are propositional variables, the statement $((p \rightarrow q) \wedge p) \rightarrow q$ is a tautology. In particular, when both $p \rightarrow q$ and $p$ are true, we know that $q$ must also be true. This would be a valid argument because whenever all its premises (all statements in the argument other than the final one, the conclusion) are ture, the conclusion must also be true.
# 1 Rules of Inference for Propositional Statements
A truth table can always be used to show that an argument form is valid. This process can be tedious however, instead we can establish validity using the rules of inference.

The tautology $(p \wedge (p \rightarrow q)) \rightarrow q$ is the basis of the rule of inference called "*modus ponens*", or the *law of detachment*. This tautology leads to the following valid argument form
$$
\begin{array}{l}
p \\
p \rightarrow q \\
\hline
\therefore q
\end{array}
$$
Suppose the conditional statement "If it snows today, then we will go skiing" and its hypothesis, "it is snowing today", are true. Then, by modus ponens, it follows that the conclusion of the conditional statement, "We will go skiing," is true.
![[87699.png]]
## 1.1 Building Arguments with Rules of Inference
When there are many premises, several rules of inference are often needed to show that an argument is valid. 
### 1.1.1 Example 1
Show that the premises "It is not sunny this afternoon and it is colder than yesterday," "We will go swimming only if it is sunny," "If we do not go swimming, then we will take a canoe trip," and "If we take a canoe trip, then we will be home by sunset" lead to the conclusion "We will be home by sunset."
Let $p$ be the proposition "It is sunny this afternoon," $q$ be the proposition "It is colder than yesterday," $r$ the proposition "We will go swimming," $s$ the proposition "We will take a canoe trip," and $t$ the proposition "We will be home by sunset." Then the premises become $\neg p \wedge q, r \rightarrow p, \neg r \rightarrow s$, and $s \rightarrow t$ and conclusion $t$.

We construct an argument to show that our premises lead to the desired conclusion as follows.

| Step                      | Reason                          |
| ------------------------- | ------------------------------- |
| 1. $\neg p \wedge q$      | Premise                         |
| 2. $\neq p$               | Simplification using (1)        |
| 3. $r \rightarrow p$      | Premise                         |
| 4. $\neg r$               | Modus tollens using (2) and (3) |
| 5. $\neg r \rightarrow s$ | Premise                         |
| 6. $s$                    | Modus ponens using (4) and (5)  |
| 7. $s \rightarrow t$      | Premise                         |
| 8. $t$                    | Modus ponens using (6) (7)      |
Note that a truth table could have been applied instead, but with five propositional variables, $p,q,r,s,t$, such a table would have 32 rows.
# 2 Fallacies
Several common fallacies arise in incorrect arguments. They resemble rules of inference but are based on contingencies rather than tautologies. The proposition $((p \rightarrow q) \wedge q) \rightarrow p$ is not a tautology, because it is false when $p$ is false and $q$ is true. However, there are many incorrect arguments that treat this as a tautology. I.e. they treat the argument with premises $p \rightarrow q$ and $q$ and conclusion $p$ as a valid argument form, which it is not. This type of incorrect reasoning is called the *fallacy of affirming the conclusion*.
# 3 Rules of Inference for Quantified Statements
![[4185.png]]
***Universal instantiation*** is the rule of inference used to conclude that $P(c)$ is true, where $c$ is a particular member of the domain, given the premise $\forall x P(x)$. Universal instantiation is used when we conclude from the statement "All women are wise" that "Lisa is wise," where Lisa is a member of the domain of all women.

***Universal generalization*** is the rule of inference that states that $\forall x P(x)$ is true, given the premise that $P(c)$ is true by taking an arbitrary element $c$ from the domain and showing that $P(c)$ is true. The element $c$ that we select must be an arbitrary, and not a specific, element of the domain. That is, when we assert from $\forall x P(x)$ the existence of an element $c$ in the domain, we have no control over $c$ and cannot make any other assumptions about $c$ other than it comes from the domain. Universal generalization is used implicitly in many proofs in mathematics and is seldom mentioned explicitly. However, the error of adding unwarranted assumptions about the arbitrary element $c$ when universal generalization is used is all too common in incorrect reasoning.

***Existential instantiation*** is the rule that allows us to conclude that there is an element $c$ in the domain for which $P(c)$ is true if we know that $\exists x P(x)$ is true. We cannot select an arbitrary value of $c$ here, but rather it must be a $c$ for which $P(c)$ is true. Usually we have no knowledge of what $c$ is, only that it exists. Because it exists, we may give it a name $(c)$ and continue our argument.

***Existential generalization*** is the rule of inference that is used to conclude that $\exists x P(x)$ is true when a particular element $c$ with $P(c)$ true is known. That is, if we know one element $c$ in the domain for which $P(c)$ is true, then we know that $\exists x P(x)$ is true.
## 3.1 Examples
### 3.1.1 Example 1
Show that the premises "Everyone in this discrete mathematics class has taken a course in computer science" and "Marla is a student in this class" imply the conclusion "Marla has taken a course in computer science."
#### 3.1.1.1 Solution
Let $D(x)$ denote "$x$ is in this discrete mathematics class," and let $C(x)$ denote "$x$ has taken a course in computer science." Then the premises are $\forall x (D(x) \rightarrow C(x))$ and $D(Marla)$. The conclusion is $C(Marla)$. 

| Step                                  | Reason                           |
| ------------------------------------- | -------------------------------- |
| 1. $\forall x (D(x) \rightarrow C(x)$ | Premise                          |
| 2. $D(Marla) \rightarrow C(Marla)$    | Universal instantiation from (1) |
| 3. $D(Marla)$                         | Premise                          |
| 4. $C(Marla)$                         | Modus ponens from (2) and (3)    |
# 4 Proof Methods
To prove a theorem of the form $\forall x (P(x) \rightarrow Q(x))$, our goal is to show that $P(c) \rightarrow Q(c)$ is true, where $c$ is an arbitrary element of the domain, and then apply universal generalization. We now need to find a method to prove conditional statements.
## 4.1 Direct Proofs
A direct proof of a conditional statement $p \rightarrow q$ is constructed when the first step is the assumption that $p$ is true; subsequent steps are constructed using rules of inference, with the final step showing that $q$ must also be true.
A direct proof shows that a conditional statement $p \rightarrow q$ is true by showing that if $p$ is true, then $q$ must also be true, so that the combination $p$ true and $q$ false never occurs. In a direct proof, we assume that $p$ is true and use axioms, definitions, and previously proven theorems, together with rules of inference, to show that $q$ must also be true.
### 4.1.1 Examples
1. ***Give a direct proof of the theorem "If $n$ is an odd integer, then $n^2$ is odd."***
This theorem states $\forall n P((n) \rightarrow Q(n))$, where $P(n)$ is "$n$ is an odd integer" and $Q(n)$ is "$n^2$ is odd". 

To begin a direct proof of this theorem, we assume that the hypothesis of this conditional statement is true, namely, we assume that $n$ is odd. By the definition of an odd integer, it follows that $n=2k+1$, where $k$ is some integer. We want to show that $n^2$ is also odd. We can square both sides of the equation to obtain a new equation that expresses $n^2$. When we do this, we find that $n^2=(2k+1)^2=4k^2+4k+1=2(2k^2+2k)+1$. By the definition of an odd integer, we can conclude that $n^2$ is an odd integer (it is one more than twice an integer). Consequently, we have proved that if $n$ is an odd integer, then $n^2$ is an odd integer.
2. ***Give a direct proof that if $m$ and $n$ are both perfect squares, then $nm$ is also a perfect square. (An integer a is a perfect square if there is an integer b such that $a = b^2$.)***
To produce a proof of this theorem, we assume that the hypothesis of this conditional statement is true, namely that $m$ and $n$ are both perfect squares. 

By the definition of a perfect square, it follows that there are integers $s$ and $t$ such that $m=s^2$ and $n=t^2$. The goal of the proof is to show that $mn$ must also be a perfect square when $m$ and $n$ are. We can substitute $s^2$ for $m$ and $t^2$ for $n$. This tells us that $mn=s^2t^2$. Hence, $mn=s^2t^2=(ss)(tt)=(st)(st)=(st)^2$. By the definition of a perfect square, it follows that $mn$ is also a perfect square, because it is the square of $st$, which is an integer.
## 4.2 Proof by Contraposition
Direct proofs lead from the premises of a theorem to the conclusion. Direct proofs can sometimes reach dead ends. Proofs of theorems that do not utilize the direct method i.e. that do not start with the premises and end with the conclusion, are called *indirect proofs*.

An extremely useful type of indirect proof is known as *proof by contraposition*. Proofs by contraposition make use of the fact that the conditional statement $p \rightarrow q$ is equivalent to its contrapositive $\neg q \rightarrow \neg p$. This means that the conditional statement $p \rightarrow q$ can be proved by showing that its contrapositive, $\neg q \rightarrow \neg p$, is true. In a proof by contraposition of $p \rightarrow q$, we take $\neg q$ as the premise, and using axioms, definitions, and previously proven theorems, together with rules of inference, we show that $\neg p$ must follow. 
### 4.2.1 Examples
1. ***Prove that if $n$ is an integer and $3n+2$ is odd, then $n$ is odd.***
Here, an attempt was made with a direct proof, which failed, therefore a proof by contraposition is done instead.

The first step in a proof by contraposition is to assume that the conclusion of the conditional statment "If $3n+2$ is odd, then $n$ is odd" is false; assume that $n$ is even. Then, by the definition of an even integer, $n=2k$ for some integer $k$, we substitute $2k$ for $n$. We find that $3n+2=3(2k)+2=6k+2=2(3k+1)$ This tells us that $3n+2$ is even (because it is a multiple of 2), and therefore not odd. This is the negation of the premise of the theorem. Because the negation of the conclusion of the condition al statement implies that the hypothesis is false, the original conditional statement is true.
2. ***Prove that if $n=ab$, where $a$ and $b$ are positive integers, then $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$.*** 
Because there is no obvious way of showing that $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$ directly from the equation $n=ab$, where $a$ and $b$ are positive integers, we attempt a proof by contraposition.

The first step in a proof by contraposition is to assume that the conclusion of the conditional statement "If $n=ab$, where $a$ and $b$ are positive integers, then $a \leq \sqrt{n}$ or $b \leq \sqrt{n}$" is false. That is, we assume that the statement $(a \leq \sqrt{n}) \vee (ab \leq \sqrt{n})$ is false. Using the meaning of disjunction together with De Morgan's law, we see that this implies that both $a \leq \sqrt{n}$ and $b \leq \sqrt{n}$ are false. This implies that $a > \sqrt{n}$ and $b > \sqrt{n}$. We can multiply these inequalities together (using the fact that $0<s<t$ and $0<u<v$, then $su<tv$) to obtain $ab > \sqrt{n} \cdot \sqrt{n}=n$ This shows that $ab \neq n$, which contradicts the statement $n=ab$. 

Because the negation of the conclusion of the conditional statement implies that the hypothesis is false, the original conditional statement is true.
## 4.3 Proofs by Contradiction
Suppose we want to prove that a statement $p$ is true. Furthermore, suppose that we can find a contradiction $q$ such that $\neg p \rightarrow q$ is true. Because $q$ is false, but $\neg p \rightarrow q$ is true, we can conclude that $\neg p$ is false, which means that $p$ is true. How can we find a contradiction $q$ that might help us prove that $p$ is true in this way?

Because the statement $r \wedge \neg r$ is a contradiction whenever $r$ is a proposition, we can prove that $p$ is true if we can show that $\neg p \rightarrow (r \wedge \neg r)$ is true for some proposition $r$. Proofs of this type are called *proofs by contradiction*. Because a proof by contradiction does not prove a result directly, it is another type of indirect proof.
### 4.3.1 Examples
1. ***Show that at least four of any 22 days must fall on the same day of the week.***
Let $p$ be the proposition "At least four of 22 chosen days fall on the same day of the week." Suppose that $\neg p$ is true. This means that at most 3 of the 22 days fall on the same day of the week. Because there are 7 days of the week, this implies that at most 21 days could have been chosen, as for each of the days of the week, at most three of the chosen days could fall on that day. This contradicts the premise that we have 22 days under consideration. That is, if $r$ is the statement that 22 days are chosen, then we have shown that $\neg p \rightarrow (r \wedge \neg r)$. 
2. ***Prove that $\sqrt{2}$ is irrational by giving a proof by contradiction.***
Let $p$ be the proposition "$\sqrt{2}$ is irrational." To start a proof by contradiction, we suppose that $\neg p$ is true. Note that $\neg p$ is the statement "It is not the case that $\sqrt 2$ is irrational," which says that $\sqrt 2$ is rational. We will show that assuming that $\neg p$ is true leads to a contradiction.

If $\sqrt 2$ is rational, there exists integers $a$ and $b$ with $\sqrt 2 = a/b$, where $b \neq 0$ and $a$ and $b$ have no common factors (so that the fraction $a/b$ is in the lowest terms). (Here, we are using the fact that every rational number can be written in lowest terms.) Because $\sqrt 2 = a/b$, when both sides of this equation are squared, it follows that 
$$
2= \dfrac{a^2}{b^2}
$$
Hence,
$$
2b^2=a^2
$$
By the definition of an even integer it follows that $a^2$ is even. We next use the fact that if $a^2$ is even, $a$ must also be even. Furthermore, because $a$ is even, by the definition of an even integer, $a=2c$ for some integer $c$. Thus,
$$
2b^2=4c^2.
$$
Dividing both sides by 2 gives
$$
b^2=2c^2.
$$
By the definition of even, this means that $b^2$ is even. Again using the fact that if the square of an integer is even, then the integer itself must be even, we conclude that $b$ must be even as well.

We have now shown that the assumption of $\neg p$ leads to the equation $\sqrt 2 = a/b$, where $a$ and $b$ have no common factors, but both $a$ and $b$ are even, that is, 2 divides both $a$ and $b$. 

Note that the statement that $\sqrt 2 = a/b$, where $a$ and $b$ have no common factors, means, in particular, that 2 does not divide both $a$ and $b$. Because our assumption of $\neg p$ leads to the contradiction that 2 divides both $a$ and $b$ and 2 does not divide both $a$ and $b$, $\neg p$ must be false. That is, the statement $p$, "$\sqrt 2$ is irrational," is true.
3. ***Give a proof by contradiction of the theorem "If $3n+2$ is odd, then $n$ is odd."***
Let $p$ be "$3n+2$ is odd" and $q$ be "$n$ is odd". To construct a proof by contradiction, assume that both $p$ and $\neg q$ are true. That is, assume that $3n+2$ is odd and that $n$ is not odd.

Because $n$ is not odd, we know that it is even. Because $n$ is even, there is an integer $k$ such that $n=2k$. This implies that $3n+2=3(2k)+2=6k+2=2(3k+1)$. Because $3n+2$ is $2t$, where $t=3k+1$, $3n+2$ is even. Note that the statement "$3n+2$ is even" is equivalent to the statement $\neg p$, because an integer is even if and only if it is not odd.

Because both $p$ and $\neg p$ are true, we have a contradiction.
## 4.4 Vacuous and Trivial Proofs…
# 5 Definitions
## 5.1 Definition 1
An *argument* in propositional logic is a sequence of propositions. All but the final proposition in the argument are called *premises* and the final proposition is called the *conclusion*. An argument is *valid* if the truth of all its premises implies that the conclusion is true. 

An *argument form* in propositional logic is a sequence of [[Logic#1.1.1 Compound Propositions|compound propositions]] involving propositional variables. An argument form is *valid* if no matter which particular propositions are submitted for the propositional variables in its premises, the conclusion is true if the premises are all true.
## 5.2 Definition 2
The integer $n$ is even if there exists an integer $k$ such that $n=2k$, and $n$ is odd if there exists an integer $k$ such that $n=2k+1$. Two integers have the *same parity* when both are even or both are odd. They have *opposite parity* when one is even and the other is odd.