Tags : #Firefighter #pk-free 
Zettel :  20231023-1502
Status : #triage 

-----

# Firefighter Variations on $P_k$-free graphs

**Previous note:** [[202310191237  Can verify Fire strategy in poly time]]

-----

### Questions & thoughts:

Original Theorem[^1] : Let $(G, r)$ be an instance of Firefighter and let $l$ be the number of vertices on a longest induced path in $GH$ starting at $r$. No optimal strategy defends more than $l-1$ vertices.

Original proof outline:
 - Suppose a strategy $S=[v_1, \dots, v_t]$ is optimal and that $t$ is maximal among optimal strategies (i.e., $S$ deploys the largest number of defences of any optimal strategy).
 - Because $S$ is optimal, there is an induced path $P$ between the root $r$ and $v_t$ the final vertex defended such that all vertices on $P$ beside $v_t$ burn. 
 - Let $P$ be a shortest path with this property.
 - $P$ contains at least $t+1$ vertices (or else $v_t$ would burn before it could be defended) hence $t\leq l-1$.


Adapted theorem for arbitrary cost function Firefighter (to keep as general as possible?): **No optimal strategy to CFire defends more than $l-1$ vertices*

 - Let $S=[[v_{1_1}, v_{1_2}, \dots], [v_{2_1}, \dots], \dots, [v_{t_1}, \dots, v_{t_h}]]$ be an optimal strategy
- Suppose that $d=\bigcup_{s\in S}|s|$ is maximal in optimal strategies of CFire
- As $S$ is optimal, there is an induced path on burning vertices between $r$ and a neighbour of $v_{t_h}$, the final vertex defended. Let $P$ be the shortest such path and let its length be $l$.
- $P$ contains at least $d+1$ vertices, else $v_{t_h}$ would burn before it could be defended. Thus, $d\leq l-1$.



-----
 
**Consider:**


**Source:** 

[1]: Theorem 4 in [this](https://doi.org/10.1016/j.tcs.2015.11.024) paper


**Reference:** 
