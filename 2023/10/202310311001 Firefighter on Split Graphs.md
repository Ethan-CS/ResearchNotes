Tags :
Zettel :  20231031-1001
Status : #triage 

-----

# Firefighter on Split Graphs

**Previous note:** [[202310251221 CFire parameterised by treewidth]]

-----

### Questions & thoughts:

Theorem 8[^1]: Let $(G, r)$ be an instance of The Firefighter Problem such that $G$ is a connected split graph on $n$ vertices and $m$ edges. This can be solved in time $O(n+m)$ time.

**Proof.**
 - Since $G$ is a split graph, $V(G)=I\cup U$ for an independent set $I$ and clique $K$ and we can find $I$ and $K$ in $O(n+m)$ time[^2]. 
 - Assume that every vertex of $C$ has a neighbour in $I$ (otherwise, remove each vertex of $C$ with no neighbours in $I$ and add it to $I$). 
 - There are two cases to consider: $r\in K$ and $r\in I$.
*Case 1: $r\in K$.*
 - Consider any optimal strategy.
 - If first defence in $I$, fire spreads to at least every other vertex of $K$.
 - Next, can protect at most one more vertex of $I$ before fire spreads to all other vertices of $I$.
 - Hence, we can save at most 2 vertices.
 - Hence, if there is an optimal strategy that places first defence in $I$ then there is one that first protects a neighbour in $I$ of $r$ and then a vertex of $I\setminus N(R)$ if this set is non-empty.
 - We can fin

-----
 
**Consider:**


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)
[2]: Hammer, P.L., Simeone, B. The splittance of a graph. _Combinatorica_ **1**, 275–284 (1981). [DOI](https://doi.org/10.1007/BF02579333)

**Reference:** 
