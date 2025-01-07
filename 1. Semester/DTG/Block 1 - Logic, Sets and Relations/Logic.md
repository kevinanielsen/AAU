# 1 Propositional Logic
> A proposition is a declarative sentence, that is either true or false but not both.
## 1.1 Propositions
**Valid Proposition Examples**
1. Washington, D.C., is the capital of the United States of America.
2. Toronto is the capital of Canada.
3. $1 + 1 = 2$.
4. $2 + 2 = 3$.

**Invalid Proposition Examples**
1. What time is it?
2. Read this carefully.
3. $x+1=2$.
4. $x+y=z$.

### 1.1.1 Compound Propositions 
Compound propositions are propositions that are combinations of other propositions, using the above-mentioned logical connectives - negation, conjunction, disjunction, exclusive or, implication, and the biconditional operator. The following is an example of a compound proposition.
$$(p \vee \neg q) \to (p \wedge q)$$ Parentheses carries the highest precedence of all the logical connectives. After that, the order of precedence is the following:
1. $\neg$
2. $\wedge$ 
3. $\vee$
4. $\to$
5. $\leftrightarrow$
#### 1.1.1.1 Truth Tables
A compound proposition can then be split up, based on the mentioned precedence, which makes it possible to create a truth table:
![[26646.png]]

### 1.1.2 Definitions
#### 1.1.2.1 Atomic propositions
Atomic propositions are propositions that cannot be expressed in simpler terms.
#### 1.1.2.2 Negation
Negation $\neg$ is the statement that is the opposite of the value of a proposition. Let $p$ be true, then $\neg p$ would be false, since negation is the inverse or "not", therefore negation $p$ could be read as "not $p$".
#### 1.1.2.3 Conjunction
A conjunction of two propositions $p$, $q$, denoted by $p \wedge q$, could be read as "$p$ and $q$" and would only be true if both of the propositions are true.
#### 1.1.2.4 Disjunction
A disjunction of two propositions, $p, q$, denoted by $p \vee q$ could be read as $p$ or $q$ and would be true if either of the propositions are true.
![[85726.png]]
#### 1.1.2.5 Exclusive or
The Exclusive or of two propositions, $p, q$, denoted by $p \oplus q$  is true when exactly one of $p$ and $q$ is true and is false otherwise. In other words, either $p$ or $q$ should be true, but not both.
#### 1.1.2.6 Conditional Statement
The Conditional statement of two propositions is the proposition "if $p$, then $q$". It is false when $p$ is true and $q$ is false, and true otherwise. In the conditional statement $p \to q$, $p$ is called the *hypothesis* (or *antecedent* or *premise*) and $q$ is called the *conclusion* (or *consequence*).
![[5283.png]]
#### 1.1.2.7 Biconditional Statement
The Biconditional statement $p \leftrightarrow q$ is the propositional "$p$ if and only if $q$". It is true when $p$ and $q$ have the same truth values, and is false otherwise. Biconditional statements are also called **bi-implications**
![[98172.png]]
## 1.2 Propositional Equivalences
### 1.2.1 Logical Equivalences
The compound propositions $p$ and $q$ are logically equivalent if $p \leftrightarrow q$ is a tautology. Logical equivalence can be denoted with $p \equiv q$ or $p\Leftrightarrow q$.

The symbol $\equiv$ is not a logical connective, and $p \equiv q$ is not a compound proposition but rather the statement that "$p \leftrightarrow q$ is a tautology".
### 1.2.2 De Morgan Laws
There are two De Morgan laws. These laws are important as they tell us how to negate conjuctions and disjunctions. 

#### 1.2.2.1 The First Law
This law tells us how to negate a disjunction by taking the conjunction of the negations of the component propositions.
 $\neg(p \vee q) \equiv \neg p \wedge \neg q$

| $p$ | $q$ | $p \vee q$ | $\neg(p \vee q)$ | $\neg p$ | $\neg q$ | $\neg p \wedge \neg q$ |
| :-: | :-: | :--------: | :--------------: | :------: | :------: | :--------------------: |
|  T  |  T  |     T      |        F         |    F     |    F     |           F            |
|  T  |  F  |     T      |        F         |    F     |    T     |           F            |
|  F  |  T  |     T      |        F         |    T     |    F     |           F            |
|  F  |  F  |     F      |        T         |    T     |    T     |           T            |
#### 1.2.2.2 The Second Law
This law tells us how to negate a conjunction by taking the disjunction of the negations of the component propositions.
$\neg(p \vee q)\equiv \neg p \wedge \neg q$
![[8588.png]]
### 1.2.3 Definitions
#### 1.2.3.1 Tautology
A tautology is a compound proposition that is always true, no matter the truth values of the propositional variables that occur in it. 

#### 1.2.3.2 Contradiction
A contradiction is a compound proposition that is always false, no matter the truth values of the propositional variables that occur in it.

#### 1.2.3.3 Contingency
A contingency is a compound proposition that is neither a tautology nor a contradiction.

![[31871.png]]
![[16941.png]]
# 2 Predicates and Quantifiers
Propositional logic is not adequate for expressing all statements in mathematics and in natural language. Therefore we use predicates and quantifiers to express those statements which are not just simply a true or false.
## 2.1 Predicates
A statement "$x$ is greater than 3" is the combination of a *subject* $x$ and a predicate "is greater than 3". Once a value is assigned to the variable x, then the statement becomes a propositional statement, until that, we call it a propositional function. 
An example of a propositional function could be $P(x)$ where "x > 3". The outcome of this function could be either true or false, depending on what we assign $x$. $P(4)$ would be true, but $P(2)$ would be false.
## 2.2 Quantifiers
When the variables in a propositional function are assigned values, the resulting statement becomes a proposition with a certain truth value. Quantification is used to create a proposition from a propositional function. Quantification expresses the extent to which a predicate is true over a range of elements.

#### 2.2.1.1 The Universal Quantifier
The universal quantification of $P(x)$ is the statement "$P(x)$ for all values of x in the domain." The notation $\forall x P(x)$ denotes the universal quantification of $P(x)$. Here $\forall$ is called the universal quantifier.

The notation $\forall$ is read as "For all" or "For every"
#### 2.2.1.2 The Existential Quantifier
The existential quantification of $P(x)$ is the proposition "There exists an element x in the domain such that $P(x)$". The notation used for the existential quantification of $P(x)$ is $\exists x P(x)$  and is read as "There is an $x$ such that $P(x)$"

The notation $\exists$ is read as "Exists". 
# Normal Forms
Normal forms are standardized ways to represent a logical proposition. 
## Elementary Conjunctions
If a [[Logic#1.1.2.3 Conjunction|conjunction]] only contains variables or their negations, we refer to it as elementary.  $p\wedge q$ or $\neg q \wedge r \wedge \neg s \wedge t$ are examples of elementary conjunctions while $(p \rightarrow q) \wedge s$ is not.

If an elementary conjunction contains both a variable and its negation then it is a contradiction. I.e. a conjunction of the form $p \wedge \neg p \wedge \cdots$ is equivalent to $\mathbb{F} \wedge \cdots$ which is always false and hence equivalent to $\mathbb{F}$. 
## Elementary Disjunctions
Analogously, we say that a disjunction is elementary if it only contains variables or their negation. The propositions $p \vee q$ and $p \vee \neg q \vee s$ are hence elementary disjunctions. 

Contrary to conjunctions we see that if an elementary disjunction contains both a variable and its negation, then it is a [[Logic#1.2.3.1 Tautology|tautology]]. Given $p \vee \neg p \vee \cdots$ we see that it is equivalent to $\mathbb{T} \vee \cdots$ which is always true and hence equivalent to $\mathbb{T}$.
## Disjunctive Normal Form
> A proposition is said to be in disjunctive normal form, if it consists of the disjunction of elementary conjunctions.

Examples of propositions in DNF are $(p \wedge q) \vee  \neg p \vee (p \wedge \neg r) \vee (\neg q \wedge r)$ and $(q \wedge r) \vee (p \wedge \neg p )$. Note that the second proposition contains the elementary conjunction $(p \wedge \neg p)$ which is a contradiction and can therefore be removed from the disjunction. We can reduce the example to $q \wedge r$. 

Every proposition can be rewritten into DNF by using the equivalences $p \rightarrow q \equiv \neg p \vee q$, [[Logic#1.2.2 De Morgan Laws|De Morgan's Laws]], and distributivity.
### Examples
1. Rewrite $(\neg p \rightarrow q) \wedge q$ into DNF.
$$ 
\begin{align}
&(q \vee \neg(\neg p)) \wedge q &(\text{Equivalence for} \rightarrow) \\
&(q \vee p) \wedge q \\
&(q \wedge q) \vee (p \wedge q) &(\text{Distributive Law})
\end{align}
$$
The expression is now in DNF
## Conjunctive Normal Form
> A proposition is said to be in conjunctive normal form, if it consists of conjunctions of elementary disjunctions.

Examples of CNF are $p \wedge(q \vee \neg s), (\neg q \vee \neg s) \wedge (p \vee s) \wedge q$ and $(p \vee s) \wedge (q \vee \neg q)$.

### Examples
1. Rewrite $(\neg p \rightarrow q) \wedge q$ into CNF
$$ 
\begin{align}
&(q \vee \neg (\neg p)) \wedge q &(\text{Equivalence for} \rightarrow) \\
&(q \vee p) \wedge q
\end{align}
$$
This expression is now in CNF
## Minterm
A minterm of $n$ variables is a conjunction, that for each variable either contains it or its negation, but not both. This means that all possible minterms for $p$ or $q$ are
$$ 
\begin{align}
&p \wedge q &&p \wedge \neg q &&\neg p \wedge q &&\neg p \wedge \neg q,
\end{align}
$$
since we consider $p \wedge q$ and $q \wedge p$ the same. A minterm is only true for exactly one set of truth values for the involved variables.
## Maxterm
If we remove all conjunctions in a minterm with disjunctions we get what is called a maxterm. Hence the maxterms for two variables $p$ and $q$ are
$$ 
\begin{align}
&p \vee q &&p \vee \neg q && \neg p \vee q && \neg p \vee \neg q.
\end{align}
$$
## Principal Disjunctive Normal Form
> A proposition is said to be in PDNF, if it is the disjunction of minterms.

### Examples
1. Truth table for the proposition $p \rightarrow q$ is given by

| $p$ | $q$ | $p \rightarrow q$ |
| --- | --- | ----------------- |
| T   | T   | T                 |
| T   | F   | F                 |
| F   | T   | T                 |
| F   | F   | T                 |
Consider each row in which the proposition is true. The proposition is true, exactly of $p \wedge q, \neg p \wedge q$ or $\neg p \wedge \neg q$ is true. This corresponds to the proposition
$$
(p \wedge q) \vee (\neg p \wedge q) \vee (\neg p \wedge \neg q)
$$
Which is in PDNF.

The process is the same as with the [[Logic#Disjunctive Normal Form|DNF]], except that we remove conjunctions that represent contradictions, and add variables to those elementary conjunctions that are not minterms. Furthermore we remove duplicates among the minterms.
2. Rewrite the DNF $(q \wedge q) \vee (p \wedge q)$ as a PDNF
$$ 
\begin{align}
&(\mathbb{T} \wedge q) \vee (p \wedge q) &(\text{Identity Law}) \\
&((p \vee \neg p)\wedge q)\vee(p \wedge q) \\
&((p \wedge q)\vee(\neg p \wedge q) \vee (p \wedge q)) &(\text{Distributive Law}) \\
&(p \wedge q) \vee (\neg p \wedge q) &(\text{Remove duplicate terms})
\end{align}
$$
The proposition is now in PDNF.
## Principal Conjunctive Normal Form
> A proposition is said to be in PCNF, if it is the conjunction of maxterms
### Examples
1. Rewrite the proposition $(q \vee p) \wedge q$ as a PCNF.
$$ 
\begin{align}
&(q \vee p) \wedge (q \vee \mathbb{F}) &(\text{Identity Law}) \\
&(q \vee p) \wedge (q \vee (p \wedge \neg p)) \\
&(q \vee p) \wedge (q \vee p) \wedge (q \vee \neg p) &(\text{Distributive Law}) \\
&(q \vee p) \wedge (q \vee \neg p) &(\text{Remove duplicate terms})
\end{align}
$$
2. The proposition $(\neg p \vee \neg q) \wedge (q \vee \neg p)$ is already in PCNF.