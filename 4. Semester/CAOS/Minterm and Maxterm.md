> Maxterm: OR relation between variables
> Minterm: AND relation between variables

==Boolean functions expressed as a sum of minterms or product of maxterms are said to be in canonical form==

Converting a boolean function into its standard forms—**Sum of Minterms (Canonical SOP)** or **Product of Maxterms (Canonical POS)**—is essentially about identifying exactly which combinations of inputs result in a `1` or a `0`.

Here is the most straightforward way to do it using a truth table or algebraic expansion.

---

## 1. Using a Truth Table (The Easiest Way)

The truth table is the "cheat sheet" for finding both forms simultaneously.

1. **List all input combinations** (e.g., for $A, B, C$, you have $2^3 = 8$ rows).
2. **Evaluate the function $F$** for every row.
3. **Identify the Minterms ($m$):** Look for the rows where $F = 1$.
4. **Identify the Maxterms ($M$):** Look for the rows where $F = 0$.
### Sum of Minterms ($\sum m$)
- For every row where $F=1$, write a product term.
- If the variable is 0, use the **complement** ($\bar{A}$). If it is 1, use the **literal** ($A$).
- **Example:** If $A=1, B=0, C=1$ produces a 1, the minterm is $A\bar{B}C$.
### Product of Maxterms ($\prod M$)
- For every row where $F=0$, write a sum term.
- **The logic is swapped:** If the variable is 0, use the **literal** ($A$). If it is 1, use the **complement** ($\bar{A}$).
- **Example:** If $A=1, B=0, C=0$ produces a 0, the maxterm is $(\bar{A}+B+C)$.
---
## 2. Algebraic Expansion (The "No-Table" Way)
If you don't want to draw a table, you can use the **Expansion Theorem** to "force" missing variables into your terms.
### To get Sum of Minterms:
Multiply any term missing a variable by $(X + \bar{X})$, which is equal to 1.
- **Function:** $F = AB + C$
- $AB$ is missing $C$: $AB(C + \bar{C}) = ABC + AB\bar{C}$
- $C$ is missing $A, B$: $C(A + \bar{A})(B + \bar{B}) = ABC + A\bar{B}C + \bar{A}BC + \bar{A}\bar{B}C$
- **Final Result:** Combine and remove duplicates.
### To get Product of Maxterms:
Use the distributive law $X + (YZ) = (X+Y)(X+Z)$ and add $X\bar{X}$ (which is 0) to terms missing a variable.
- **Function:** $F = (A+B)(A+C)$
- $(A+B)$ is missing $C$: $(A+B) + C\bar{C} = (A+B+C)(A+B+\bar{C})$
- **Final Result:** The product of those expanded sums.
---
## Quick Reference Summary

|**Feature**|**Minterm (m)**|**Maxterm (M)**|
|---|---|---|
|**Function Value**|$F = 1$|$F = 0$|
|**Operation**|Product (AND)|Sum (OR)|
|**Variable = 0**|Complemented ($\bar{A}$)|Normal ($A$)|
|**Variable = 1**|Normal ($A$)|Complemented ($\bar{A}$)|
|**Notation**|$\sum m(1, 3, \dots)$|$\prod M(0, 2, \dots)$|
