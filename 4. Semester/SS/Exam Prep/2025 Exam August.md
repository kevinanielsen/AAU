# Exercise 1
## a.
![[02 - Areas/AAU/4. Semester/SS/Exam Prep/Media/2025 Exam August/Image 2.jpeg]]
## b.
![[02 - Areas/AAU/4. Semester/SS/Exam Prep/Media/2025 Exam August/Image 3.jpeg]]
## c.
![[Image 4.jpeg]]
## d.
$R_4=(1\cup 2) \cup (123^\star 1)$
## e.
$R_5=123^\star1$
# Exercise 2
## a.
### i.
![[02 - Areas/AAU/4. Semester/SS/Exam Prep/Media/2025 Exam August/Image.jpeg]]
### ii.
![[Image 7.jpeg]]
### iii.
![[Image 8.jpeg]]

## b.
### i.
NFA:

| $\delta$ | a     | b     | c     |
| -------- | ----- | ----- | ----- |
| $q_1$    |       | $q_2$ |       |
| $q_2$    | $q_2$ | $q_2$ | $q_1$ |
DFA:

| $\delta$    | a           | b           | c           |
| ----------- | ----------- | ----------- | ----------- |
| $\{q_1\}$   | $\emptyset$ | $\{q_2\}$   | $\emptyset$ |
| $\{q_2\}$   | $\{q_2\}$   | $\{q_2\}$   | $\{q_1\}$   |
| $\emptyset$ | $\emptyset$ | $\emptyset$ | $\emptyset$ |
![[Image 9.jpeg]]
### ii.
NFA:

| $\delta$ | a     | b     | c   |
| -------- | ----- | ----- | --- |
| $q_3$    |       |       |     |
| $q_4$    | $q_3$ | $q_3$ |     |
DFA:

| $\delta$       | a              | b              | c           |
| -------------- | -------------- | -------------- | ----------- |
| $\{q_3, q_4\}$ | $\{q_3, q_4\}$ | $\{q_3, q_4\}$ | $\emptyset$ |
| $\emptyset$    | $\emptyset$    | $\emptyset$    | $\emptyset$ |
![[Image 10.jpeg]]
### iii.
NFA:

| $\delta$ | a     | b     | c     |
| -------- | ----- | ----- | ----- |
| $q_1$    |       | $q_2$ |       |
| $q_2$    | $q_2$ | $q_2$ | $q_1$ |
| $q_3$    |       | $q_4$ |       |
| $q_4$    | $q_4$ | $q_4$ | $q_3$ |
DFA:

| $\delta$       | a              | b              | c              |
| -------------- | -------------- | -------------- | -------------- |
| $\{q_1, q_3\}$ | $\emptyset$    | $\{q_2, q_4\}$ | $\emptyset$    |
| $\{q_2, q_4\}$ | $\{q_2, q_4\}$ | $\{q_2, q_4\}$ | $\{q_1, q_3\}$ |
| $\emptyset$    | $\emptyset$    | $\emptyset$    | $\emptyset$    |
![[Image 11.jpeg]]
## c.
NFA
## d.
both
# Exercise 3
## a.
$V=\{A, B, C\}$
$\Sigma=\{a, b, c, d, e\}$
$S=A$
$R =\{(A, aBbBcBdBe), (B, \epsilon), (B, CA), (B, aA), (C, a), (C, b)\}$
## b.
### i.
Yes
### ii.
No
### iii.
No
The arrow $\Rightarrow$ denotes a _single_ derivation step. $A\to abcde$ is not a rule in the grammar $R$.
### iv.
Yes
### v.
Yes
### vi.
Yes
## c.
abcde, abcdaabcdee, abcaabcdede
## d.
a, b, c, d, e
## e.
Yes. The string $abcdaAe$ can be reached with either $A\Rightarrow aBbBcBdBe \Rightarrow abcdCAe\Rightarrow abcdaAe$, or 
$A\Rightarrow aBbBcBdBe\Rightarrow abcdaAe$.

If a string can have different derivation trees, it is ambiguous.
# Exercise 4
# Exercise 5
## a.
$$
\dfrac{s \vdash a \to_A v}{\langle x \text{ += } a, s\rangle \to s[x\mapsto s(x)+v]}
$$
## b.
$s=[x\mapsto6,y\mapsto3]$
$s'=[x\mapsto9,y\mapsto3]$
$$
\dfrac{\dfrac{s\vdash x \to_A 6 \quad s\vdash 5 \to_A 5}
{\langle x > \underline5, s \rangle \to \top} \quad 
\dfrac{s \vdash y \to 3}
{\langle x \text{ += } y, s \rangle \to s'}}
{\langle \texttt{if $x>\underline5$ then $x\text{ += } y$ else skip}, s\rangle \to s'}
$$
## c.
$s_1=[x\mapsto 3, y\mapsto 3]$
$s_2=[x\mapsto 3, y\mapsto 3]$
$s_3=[x\mapsto 6, y\mapsto 3]$
## d.
$s=[x\mapsto 0, y\mapsto 0]$
# Exercise 6
## a.
$$
\dfrac{E \vdash x: \text{Int} \quad E \vdash e: \text{Int}}
{E \vdash x \text{ += } e: \text{ok}}
$$
## b
$$
\dfrac{
    \dfrac{
        \dfrac{
            E\vdash x:\text{Int} \quad
            \dfrac{
                \dfrac{
                    E \vdash 4:\text{Int} \quad E\vdash x:\text{Int}
                }{E \vdash 4*x:\text{Int}} 
            }{E \vdash (4*x):\text{Int}} 
        }{E \vdash x=(4*x):\text{Bool}} 
    }{E \vdash (x=(4*x)):\text{Bool}} 
    \quad
    E \vdash y:\text{Bool}
}{E \vdash (x=(4*x)) \wedge y:\text{Bool}}
$$