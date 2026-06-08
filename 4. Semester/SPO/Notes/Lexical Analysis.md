A lexical analyzer is a finite automaton for the “union” of all regular expressions describing the tokens.
However, it differs from the mere analysis of a single word by an automaton, since
- we must split the input into a sequence of words
- there are possible ambiguities
- we have to build tokens (final states contain actions)
Lexical analysis uses: 
- regular expressions
- finite automata
## Ambiguities
the word is recognized by the regular expression for identifiers, but contains a prefix recognized by another regular expression (keyword fun)
$\Rightarrow$ we choose to match the longest token

the word `fun` is recognized by the regular expression for the keyword `fun` but also by that of identifiers.
$\Rightarrow$ we order regular expressions using priorities.
## No backtracking
With the three regular expressions
$$a, ab, bc$$
a lexical analyzer will fail on input

$$abc$$
(ab is recognized, as longest, then failure on c)
yet the word $abc$ belongs to the language $(a|ab|bc)⋆$ 
