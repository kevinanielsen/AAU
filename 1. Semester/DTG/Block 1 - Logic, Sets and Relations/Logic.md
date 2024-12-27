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
$$(p \vee \neg q) \to (p \wedge q)$$ Parentheses carries the highest precedence of all the logical connectives. After that, the order of precedence is the following:
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