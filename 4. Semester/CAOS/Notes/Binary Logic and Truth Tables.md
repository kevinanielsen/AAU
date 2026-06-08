# Binary Logic
![[binary logic.png|Binary Logic|600]]
![[logic gates with more than two variables.png|Logic Gate with more than two variables|600]]
![[other logic gates.png|Other logic gates|600]]
![[basic laws.png|Basic Laws|600]]
![[basic theorems.png|Basic Theorems|600]]
## Boolean Functions
### Precedence
The operator precedence for evaluating boolean expressions is
1. Parentheses
2. NOT
3. AND
4. OR
# Truth Tables
![[boolean functions and truth tables.png|Boolean Functions and Truth Tables|600]]
![[boolean functions with logic gates and truth tables.png|Boolean Functions with Logic Gates|600]]
## Boolean Functions in Minterms and Maxterms

A binary variable may appear either in its normal form (x) or in its complement form (x’)

**Minterm**: AND relation between variables
- Each variable being primed (x') if the corresponding bit of the binary number is 0 and unprimed (x) if 1
**A minterm is just a row in a truth table that outputs a 1**. It is an `AND` expression that includes every single variable in the circuit. For example, if variables $x=1,y=0,z=1$ produce an output of `1`, the minterm is $xy′z$. The "Sum of Minterms" is just `OR`ing together all the rows that resulted in a 1.

**A maxterm is just a row in a truth table that outputs a 0**. It is an `OR` expression of all variables. The "Product of Maxterms" is `AND`ing together all the rows that resulted in a 0.
**Maxterm**: OR relation between variables
- Each variable being primed (x') if the corresponding bit of the binary number is a 1 and unprimed (x) if a 0

Boolean functions expressed as a sum of **minterms** or product of **maxterms** are said to be in **canonical form**
- **Each term must include all the variables**


