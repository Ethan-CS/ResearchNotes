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
 - If first defence is $v\in I$, 
	 - Fire spreads to at least every other vertex of $K$.
	 - Next, can protect at most one more vertex of $I$ before fire spreads to all other vertices of $I$.
	 - Hence, we can save at most 2 vertices.
	 - Hence, if there is an optimal strategy that places first defence in $I$ then there is one that first protects a neighbour in $I$ of $r$ and then a vertex of $I\setminus N(R)$ if this set is non-empty.
	 - We can find such a strategy in $O(n+m)$ time.
 - Else first defence is $v\in K$.
	 - Fire spreads to at least every vertex of $K\setminus\{v\}$ 
	 - If $v$ has neighbours of degree 1, these are saved by protecting $v$
	 - Then, we can defend at most one more vertex $w\in I$ not adjacent to $r$ before fire spreads to all other vertices of $I$.
	 - Thus, an optimal strategy with first defence in $K$:
		 - First protects a vertex $v\neq r$ in $K$ with highest number of neighbours of degree 1
		 - Then trues to defend a vertex $w\in I$ neither (a neighbour of $r$) nor (neighbour of $v$ and degree 1) if such a $w$ exists.
	 - Vertices $v$ and $w$ (and hence such an optimal strategy) can be found in $O(n+m)$ time.

Case 2: $r\in I$.
 - If $\textrm{deg}(r)=1$, it is optimal to protect the single neighbour of $r$ in $K$, saving all vertices in $G\setminus\{r\}$
 - Hence, assume $\textrm{deg}(r)\geq 2$.
 - Note split graphs are $P_5$-free - then by [[202310231502 FF Optimal strategy number of defences|a previous lemma]], we can protect at most three vertices.
 - Suppose there is an optimal strategy that defends only in $I$
	 - Fire spreads first from $r$ to every vertex of $N(r)\subseteq K$, then to at least every vertex in rest of $K$ (minus one defence), then to unprotected vertices of $I$ (again, less one defence).
	 - Hence, any such strategy saves at most three vertices.
	 - Hence, if there is such an optimal strategy only protecting vertices from $I$, in first two time-steps it protects a neighbour in $I\setminus\{r\}$ of a vertex in $N(r)$ or any other vertex of $I\setminus\{r\}$ otherwise, then a vertex of $I$ not neighbouring any vertex in $I\setminus\{r\}$ if it exists.
	 - We can find such a strategy in $O(n+m)$ time.
 - Suppose there is an optimal strategy that defends two or more vertices from $K$.
	 - Since $r$ has degree at least 2, fire first spreads to at least one vertex in $K$, then to unprotected vertices of $K$.
	 - Since $r$ has degree at least 2 by assumption, fire spreads first to at least one vertex of $K$, then to all other unprotected vertices of $K$.
	 - Such an optimal strategy protects exactly two vertices $u, v\in K$

-----
 
**Consider:**


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)
[2]: Hammer, P.L., Simeone, B. The splittance of a graph. _Combinatorica_ **1**, 275–284 (1981). [DOI](https://doi.org/10.1007/BF02579333)

**Reference:** 
