# 1 How it Works
## 1.1 The Stack
- **$T$ (Terminals):** These are the actual characters or tokens from your input string (e.g., `id`, `+`, `(`, `)`).
- **$N$ (Non-terminals):** These are the variables or categories defined in your grammar rules (e.g., $Expr$, $Term$, $Factor$).
- **$(T \cup N)^*$:** The $\cup$ means union, and the $^*$ (Kleene star) means "zero or more occurrences." This notation simply means that the parser's stack can hold a sequence of _both_ terminals and non-terminals at any given time.
## 1.2 The Two Primary Actions
- **Shift:** The parser reads the next terminal symbol from the input stream and pushes it onto the top of the stack.
- **Reduce:** This is where the "bottom-up" magic happens. The parser looks at the top of the stack. If the symbols at the top exactly match the right-hand side ($\beta$) of a known grammar production rule ($X \rightarrow \beta$), it "reduces" them. It pops $\beta$ off the stack and replaces it with the left-hand side ($X$).
# 2 Differences from [[Top-Down Parsing (LL(1))]]
In the top-down parsing, the crux was to be able to decide which action to perform on a stack reading the current token of the input.
- that tool was the expansion table $T (X ,a)$,
- the subtlety was to construct it using $\text{FIRST}$, $\text{FOLLOW}$ & $\text{NULL}$ sets.

In bottom-up parsing, the crux is to be able to decide how to choose between shift and reduce when reading a given token of the input;
- That tool is a deterministic finite automaton whose transitions are labeled by $x_i \in T \cup N$ and states are stored on the stack alongside those symbols, i.e. the stack looks like ${\color{red}s_0} \; x_1 {\color{red}s_1} \; x_2 \; \dots \; x_n \; {\color{red}s_n}$
- The subtlety is that the states are items of the form $[X \to α \bullet β]$ where $X →αβ$ is a grammar production; the intuition is “we want to recognize $X$ , we’ve already seen $α$, but we still need to see $β$”
# 3 How to Choose Between Shift and Reduce
- Using a finite deterministic automaton whose states are stored on the stack alongside grammar symbols $x \in T \cup N$.
- And considering the first $k$ tokens of the input.
This is called LR(k) analysis
(LR means “Left to right scanning, Rightmost derivation”)
in practice $k = 1$, i.e., we only consider the first token to take the decision.
# 4 LR Analysis
## 4.1 The Stack Now Remembers "States"
Instead of just pushing grammar symbols (terminals and non-terminals) onto the stack, the parser pushes **states** ($s_0, s_1, \dots, s_n$) alongside them.
- **Stack:** $s_0$ `(symbol)` $s_1$ `(symbol)` $s_2$
- **Why?** The state at the very top of the stack ($s_n$) acts as the "memory" of the parser. It encapsulates everything the parser has seen so far, so it doesn't have to scan down the stack to figure out what context it is in.
## 4.2 The Action Table (The Decision Maker)
To eliminate guessing, the parser uses a pre-computed lookup matrix called the **action table**.
At each step, it looks at two things:
1. The state currently at the top of the stack ($s_n$).
2. The next incoming token from the input ($a$).

By looking up coordinates $(s_n, a)$ in the table, it gets an absolute, deterministic command:
- **Shift:** Push the token $a$ and a new state onto the stack.
- **Reduce:** Fire a specific grammar rule.
- **Success/Failure:** The string is either fully validated or contains a syntax error.
## 4.3 The Goto Table (The Post-Reduce Router)
When the parser performs a **reduce** operation (e.g., replacing a sequence of symbols $\alpha$ with a single non-terminal $X$), it pops the symbols and their associated states off the stack.

Because the stack has changed, the parser needs to know what state it should be in now. It looks at the new top-of-stack state ($s_{n-p}$) and the newly produced non-terminal ($X$), and uses the **goto table** to find the next state ($s$) to push onto the stack.
# LR(0) Automaton
let us use $k = 0$ for the moment
we consider the following grammar:
$$
\begin{array}{rrl}
S & \rightarrow & E \\[6pt]
E & \rightarrow & E + E \\
  & \mid        & (E) \\
  & \mid        & \texttt{int}
\end{array}
$$
we start by constructing an automaton with $\epsilon$-transitions denoted by $s_1 \xrightarrow{\epsilon} s_2$.

The states are items of the form
$$[X \to \alpha \bullet \beta]$$
where $X \to αβ$ is a grammar production; the intuition is “we want to recognize $X$, we’ve already seen $α$ and we still need to see $β$”
the transitions are labeled by $T \cup N$ are as follows:
$$
\begin{array}{rcl}
[Y \to \alpha \bullet a\beta] & \xrightarrow{a} & [Y \to \alpha a \bullet \beta] \\
[Y \to \alpha \bullet X\beta] & \xrightarrow{X} & [Y \to \alpha X \bullet \beta ] \\
[Y \to \alpha \bullet X\beta] & \xrightarrow{\epsilon} & [X \to \bullet \gamma] \\
& & \text{for each production } x \to \gamma
\end{array}
$$

# 5 Example
## 5.1 Grammar
1. $S \rightarrow a S b$
2. $S \rightarrow c$
## 5.2 Input to parse: `a c b`
Here is how the shift-reduce parser would process it step-by-step:

|**Step**|**Stack**|**Remaining Input**|**Action**|**Explanation**|
|---|---|---|---|---|
|1|`(empty)`|`a c b`|**Shift**|Push the first token (`a`) onto the stack.|
|2|`a`|`c b`|**Shift**|Push the next token (`c`) onto the stack.|
|3|`a c`|`b`|**Reduce**|The top of the stack is `c`, which matches Rule 2 ($S \rightarrow c$). We replace `c` with $S$.|
|4|`a S`|`b`|**Shift**|Push the last token (`b`) onto the stack.|
|5|`a S b`|`(empty)`|**Reduce**|The top of the stack is `a S b`, which matches Rule 1 ($S \rightarrow a S b$). We replace it with $S$.|
|6|$S$|`(empty)`|**Accept!**|Input is empty, and only the axiom $S$ is left on the stack.|

