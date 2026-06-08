# Derivation Example
$$
E, b:= a + 1; \texttt{if $b > 3$ then $b:=0$ else skip }\twoheadrightarrow \{a \mapsto 4, b \mapsto 0\}
$$
The strategy: read the conclusion, identify the outermost construct, apply its rule, and repeat for each premise.
## Step 1 - Identify The Outermost Construct
The whole program is a sequence $s_1;s_2$ where $s_1 = (b:= a+ 1)$ and $s_2 = ( \texttt{if...})$. The sequencing rule requires:
$$
\dfrac{E, s_1 \twoheadrightarrow E_1 \quad E_1, s_2 \twoheadrightarrow E_2}{E, s_1;s_2 \twoheadrightarrow E_2}
$$
So we need to find $E_1$ (the environment after $s_1$) and show both premises.
## Step 2 - Evaluate The Left Premise 
$$E, b:= a+1 \twoheadrightarrow E_1$$
Assignment rule needs $E, a+1 \twoheadrightarrow v$. Addition needs both sides: $E, a\twoheadrightarrow 4$ (lookup) and $E, 1 \twoheadrightarrow 1$ (constant). So $a+1 \twoheadrightarrow 5$, giving $E_1 = \{a \mapsto 4, b \mapsto 5\}$.
## Step 3 - Evaluate The Right Premise
$$E_1, \texttt{if $b>3$ then $b:= 0$ else skip } \twoheadrightarrow E_2$$
The if-true rule needs $E_1, b > 3 \twoheadrightarrow true$. Since $b = 5$ in $E_1$, we get $5 > 3 = true$. Then we evaluate the true-branch: $E_1, b := 0 \twoheadrightarrow \{a \mapsto 4, b \mapsto 0\}$. So $E_2 = \{a \mapsto 4, b \mapsto 0\}$.
## Step 4 - Assemble The Full Tree
Now write it all as one nested fraction. Leaves at the top, conclusion at the bottom.
$$
\dfrac{\dfrac{\dfrac{\dfrac{}
{E, a \twoheadrightarrow 4} \quad \dfrac{}{E, 1 \twoheadrightarrow 1}}
{E, a+1 \twoheadrightarrow 5}}
{E, b:= a + 1 \twoheadrightarrow E_1} \quad \dfrac{
\dfrac{\overline{E_1, b \twoheadrightarrow 5} \quad \overline{E_1, 3 \twoheadrightarrow 3}}{E_1, b >3 \twoheadrightarrow true} 
\quad \dfrac{}{E_1, b :=0 \twoheadrightarrow E_2}
}
{E_1, \texttt{if $b > 3$ then $b := 0$ else skip } \twoheadrightarrow E_2}}
{E, b:= a + 1; \texttt{if $b > 3$ then $b := 0$ else skip } \twoheadrightarrow \{a \mapsto 4, b \mapsto 0\}}
$$
where $E_1= \{a \mapsto 4, b \mapsto 5\}$ and $E_2 = \{a \mapsto 4, b \mapsto 0\}$.

