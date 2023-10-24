Tags :
Zettel :  20231024-1018
Status : #triage 

-----

# Firefighter on $P_k$-free graphs

**Previous note:** [[202310231502 FF Optimal strategy number of defences]]

-----

### Questions & thoughts:

Original theorem:[^1] Firefighter can be solved in time $O(n^{k-2}(n+m))=O(n^k)$ on $P_k$-free graphs on $n$ vertices with $m$ edges.

Original proof: 
 - Let $(G, r)$ be an instance of Firefighter such that $G$ is $P_k$-free i.e., the longest induced path in $G$ has at most $k-1$ vertices
 - By [[202310231502 FF Optimal strategy number of defences|this lemma]], any optimal strategy defends at most $k-2$ vertices
 - Use the following algorithm:
	 - Enumerate all ordered subsets $S\subseteq V(G)$ of size at most $k-2$ in $O(n^{k-2})$ time.
	 - For each such $S$:
		 - Use [[202310191237  Can verify Fire strategy in poly time|this lemma]] to verify $S$ is a valid strategy and count number of saved vertices in $O(n+m)$ time.
	 - Return the valid strategy $S$ that saves the largest number of vertices

Adapted theorem: CFire can be solved in time (still the same?) on $P_k$-free graphs on $n$ vertices with $m$ edges.

Proof: as above, with adapted lemmas (in same links).

-----
 
**Consider:**


**Source:** 

[1]: Theorem 5 in [this](https://doi.org/10.1016/j.tcs.2015.11.024) paper


**Reference:** 
