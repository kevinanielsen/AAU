# 1
## a)
Let $w = 0^p 1 0^p$. 
By the Pumping Lemma, $|xy| \le p$. Because the first $p$ characters of $w$ are all $0$s, $y$ must consist entirely of zeros. 
If we pump the string with $i = 2$ ($w = xy^2z$), we add more zeros to the front. There are now more zeros before the $1$ than after, breaking the $0^n 1^m 0^n$ rule. Therefore, the language is not regular.
## b)
Let $w = ab^pc^p$. Clearly $w \in L_2$ and $|w| \ge p$.
By the Pumping Lemma, $|xy| \le p$. Because the first $p$ characters of $w$ consist of one $a$ followed by $p-1$ $b$'s, the string $y$ must fall into one of two cases:

**Case 1: $y$ contains the $a$.**
If $y$ contains the $a$, pumping the string with $i=2$ $(w=xy^2z)$ will result in a string with more than one $a$ (e.g., $aab\dots$ or $abab\dots$). This breaks the rule that strings in $L_2$ can only start with a single $a$.

**Case 2: $y$ consists entirely of $b$'s.**
If $y$ contains no $a$'s, it must be made entirely of $b$'s. If we pump the string with $i=2$, we add more $b$'s to the string but no $c$'s. This breaks the $b^nc^n$ rule.

In all valid cases, pumping the string results in a contradiction. Therefore, the language is not regular.
## c)
Let $w=0^p1^p$
By the Pumping Lemma, $|xy|\le p$. Because the first $p$ characters of $w$ are all 0s, $y$ must consist entirely of 0s.

If we pump the string with $i=2$ $(w=xy^2z)$, we add more 0s than 1s, breaking the $m=n$ rule.
## d)
- Assume $L_4$​ is regular.
- We know that the language $LR​={ab^\star c^\star}$ is regular because it can be defined by a regular expression.
- Because regular languages are closed under intersection, the language $L_{new}​=L_4​\cap L_R$​ must also be regular.
- Let's look at what $L_{new}$​ actually is. It only keeps strings from $L_4$​ that have exactly one $a$. Because $i$ is forced to be 1, the condition $j=k$ is permanently locked in. $$Lnew​={ab^nc^n∣n≥0}$$
- We already know from problem 1(b) that $\{ab^nc^n\}$ is **not regular**.
- **The Contradiction:** $L_{new}​$ cannot be both regular and not regular. Because $L_R$​ is definitely regular, our initial assumption must be wrong. Therefore, $L_4$ is not regular.
## e)
1. Assume $L_5$ is regular.
2. Because regular languages are closed under complementation, the opposite language $\overline{L_5}$ must also be regular.
3. $\overline{L_5}$ contains all strings where the number of $0$s _does_ equal the number of $1$s, but it also contains garbage strings that are out of order (like `10`, `1100`, `0101`).
4. To clean up the garbage, we intersect it with the regular language $L_R = \{0^*1^*\}$. Because both are regular, their intersection must be regular.
5. Let's look at the intersection: $\overline{L_5} \cap 0^*1^*$. It takes all strings where $m=n$, and forces them into the strict $0$s followed by $1$s order. $$L_{new} = \{0^n1^n \mid n \ge 0\}$$
6. We mathematically proved in problem 1(c) that $\{0^n1^n\}$ is **not regular**.
7. **The Contradiction:** Since the result is not regular, our assumption that $L_5$ is regular must be false. Therefore, $L_5$ is not regular.
# 2
Pumping Lemma ***Cannot*** be used to prove a language ***is*** regular.
To prove that $L$ is regular, we construct a regular expression that exactly generates $L$. 
Because $w$ cannot contain the substring $ab$, all instances of $b$ must precede all instances of $a$. 
To satisfy the parity constraints, the prefix of $b$'s must be odd, represented by $b(bb)^\star$, and the suffix of $a$'s must be even, represented by $(aa)^\star$.

Concatenating these gives the regular expression:
$R = b(bb)^\star(aa)^\star$

Since $L$ can be described by a regular expression, $L$ is a regular language.