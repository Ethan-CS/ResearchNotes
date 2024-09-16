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
 - Dynamic programming:
	 - Create a table $DP$ in which each $DP[i][t]$ for intervals up to $i$ at time $t$ representing max number of vertices that can be saved.



-----
 
**Consider:**


**Source:** 


**Reference:** 
