Tags :
Zettel :  20240916-1823
Status : #triage 

-----

# CFire on interval graphs

**Previous note:** [[202408161357 Feedback by Section]]

-----

### Questions & thoughts:


**Theorem.** CFire can be solved in time $O(?)$ on interval graphs on $n$ vertices.

(I'm not even sure this is possible, but I think it is!)

"Proof."
 - Let $G=(V, E)$ be an interval graph with $n$ vertices and $b$ be per-turn budget
 - Obtain the interval representation $I$ of $G$ (in $O(n)$-time) and sort them with respect to their right endpoints (in O(n ln(n))-time using e.g. comparison sort).
 - Dynamic programming strategy. 
	 - Construct a clique tree from $G$ by identifying maximal cliques and their intersections in $O(nw)$-time.
	 - Traverse the clique tree from leaves to root as follows. 
	 - For each clique $K$ ($O(n)$) and time step $t$ ($O(k)$), compute the maximum number of vertices that can be saved by defending each subset of $d$ vertices in $t$ time steps in $K$ ($O(2^w)$) such that $\sum_{v\in d}c(v)\leq b$
	 - To find the effect of defending in $K$ or not, recur to see how this impacts optimal defence in child cliques.
	 - Store the sub-problem solutions in a decision program table $DP[K][S\subseteq K][t]$ that evaluates to \texttt{true} if, by saving $S\subseteq K$, we can save at least $k$ vertices (and \texttt{false} otherwise). This answers the decision problem in $O(bkn\cdot 2^w)$ time.



-----
 
**Consider:**


**Source:** 


**Reference:** 
