Tags : #Firefighter #pk-free 
Zettel :  20231023-1502
Status : #triage 

-----

# Firefighter Variations on $P_k$-free graphs

**Previous note:** [[202310191237  Can verify Fire strategy in poly time]]

-----

### Questions & thoughts:

Original Theorem[^1] : **Firefighter can be solved in time $O(n^{k-2}(n+m))=O(n^k)$ on $P_k$-free graphs.**

Original proof outline:
 - Suppose a strategy $S=[v_1, \dots, v_t]$ is optimal and that $t$ is maximal among optimal strategies (i.e., $S$ deploys the largest number of defences of any optimal strategy).
 - Because $S$ is optimal, there is an induced path $P$ between the root $r$ and $v_t$ the final vertex defended such that all vertices on $P$ beside $v_t$ burn. 
 - Let $P$ be a shortest path with this property.
 - $P$ contains at least $t+1$ vertices (or else $v_t$ would burn before it could be defended).
 - Hence, $t\leq l-1$.




-----
 
**Consider:**


**Source:** 

[1]: Theorem 4 in [this](https://doi.org/10.1016/j.tcs.2015.11.024) paper


**Reference:** 
