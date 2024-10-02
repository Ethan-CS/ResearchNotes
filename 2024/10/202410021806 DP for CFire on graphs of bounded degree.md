Tags : #cfire #pk-free 
Zettel :  20241002-1806
Status : #triage 

-----

# DP for CFire on graphs of bounded degree

**Previous note:** [[202409181415 Another problem]]

-----

### Questions & thoughts:

Consider an instance of \CFF on: a rooted, $P_\ell-free$ graph $(G=(V, E), r)$ on $n$ vertices and $m$ edges, an integer $k$ and a budget $b\in\mathbb{N}$. 
- Observe that any strategy defends over at most $\ell-2$ time steps, the length of the longest path, because after this time step fire has reached every vertex it is able to reach in $G$.
- Further, observe that at time $t\leq \ell-2$ every vertex $v\in V$ with $\textrm{dist}(v, r) < t$ is burned or defended. 
So:
 - At each time $t\leq (\ell-2)$, 

```
new_disconnect(G, v) = |{u in G\{v} : dist(G\{v}, u, r) = \infty > dist(G, u, r)}|
DP(v, b, t) = 1 + new_disconnect(G, v) + max_{u in G\{v}}{DP(u, b-c(v, t), t)}
```
  

-----
 
**Consider:**


**Source:** 


**Reference:** 
