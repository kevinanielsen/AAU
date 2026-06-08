![[the_goal_of_parsing.png]]
Parsing uses:
- a context-free grammar to define the syntax
- a pushdown automaton to recognize it
# Context Free Grammar (CFG)
## Definition
A context-free grammar is a tuple $(N,T ,S,R)$ where
- $N$ is a finite set of nonterminal symbols
- $T$ is a finite set of terminal symbols
- $S\in N$ is the start symbol (the axiom)
- $R \subseteq N \times (N \cup T )^\star$ is a finite set of production rules
## Example 1: Arithmetic Expressions
![[cfg_exampe_1.png]]
## Example 2: $a^nb^n$
![[cfg_example_2.png]]
## Derivation
### Definition
A word $u \in (N \cup T)^\star$ is derived into a word $v \in (N \cup T)^\star$, which we write $u \to v$ , if there is a decomposition
$$u = u1Xu2$$
with $X \in N, X \to \beta \in R$, and
$$v = u1\beta u2$$
Example:
![[derivation_definition_example.png]]
![[derivation_example.png]]

we note $\to ^ \star$ the reflexive transitive closure of $\to$. This essentially means "derives in zero or more steps".

The language defined by a context-free grammar $G = (N,T,S,R)$ is the set of words from $T^\star$ that are derived from the axiom, i.e.
$$L(G ) = \{w \in T^\star \;|\; S \to^\star w\}$$
### Derivation Tree
A derivation tree is a tree whose nodes are labeled with grammar symbols, such that
- the root is the axiom $S$
- any internal node $X$ is a nonterminal whose subnodes are labeled by $\beta \in(N \cup T )^\star$ with $X \to \beta$ a production rule.
Example:
![[derivation_tree_example.png]]
## Ambiguity
A context-free grammar is ambiguous if at least one word accepts several derivation trees.
![[ambiguous_cfg_example.png]]and thus our grammar is ambiguous:
- the parser can’t know it should choose the left tree to build the AST
- if it chooses the right tree, it will build an AST with a wrong meaning
![[non_ambiguous_grammar_example.png]]
![[non_ambiguous_tree.png]]
whether a context-free grammar is ambiguous is not decidable.