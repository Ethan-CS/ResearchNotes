Tags :
Zettel :  20230621-1446
Status : #triage 

-----

# Satisfiability Problems

**Previous note:** [202306211411 Claim about WDF Hardness](202306211411%20Claim%20about%20WDF%20Hardness.md)

-----

### Questions & thoughts:

Proof of Firefighter being NP-Complete on graphs with max degree 3 where fire starts on degree of vertex 3 involves complex proof from 3-SAT variant. I'm going to learn about SAT problems now.

### SAT problems
-----
**SAT**
 - Instance: a boolean formula $b$
 - Question: does there exist an interpretation (a way of assigning TRUE/FALSE to literals of $b$) that satisfies (evaluates to TRUE) $b$?
-----
**3-SAT**
 - Instance: a formula in conjunctive normal form with a set of clauses each containing up to 3 literals.
 - Question: does there exist an interpretation satisfying the formula?
-----
**NAE 3-SAT (without negated literals)**
 - Instance: an ordered pair $(B, C)$ composed of a set of boolean variables $B$ and a set of clauses $C$ over $B$ in CNF each containing exactly 3 non-negative literals.
 - Question: does there exist an interpretation for $B$ such that every clause in $C$ contains at least one true literal and one false literal?
-----
**RESTRICTED NAE 3-SAT**
 - Instance: an ordered pair $(B, C)$ consisting of a set $B$ of boolean literals and a set $C$ of clauses over $B$ in CNF where $|B|=2^m$ for some integer $m\geq2$, exactly $|C|/2$ clauses have no negated literals and the remaining clauses are obtained from these by replacing each literal with its negation.
 - Question: is there an interpretation for $B$ such that every clause in $C$ contains at least one true literal and at least one false literal?
-----

