Tags : #cfire 
Zettel :  20231031-1347
Status : #triage 

-----

# Trying to prove CFire number of defended vertices again

**Previous note:** [[202310311001 Firefighter on Split Graphs]]

-----

### Questions & thoughts:

**Lemma:** Let $\mathcal{I}$ be an instance of \CFire on a rooted graph $(G=(V, E), r)$ with integer $k\geq 1$, a cost function $c:V\rightarrow \mathbb{Z}$, and a protection budget $b$. Let $\ell$ be the number of vertices on a longest induced path in $G$ starting from $r$. Then, in \CFire, no optimal strategy can protect more than $\ell - 1$ vertices.

**Proof:**

1. Consider an optimal strategy for \CFire $D=(({d_{1_1}, d_{1_2}, \dots)}, ({d_{2_1}, \dots}), \dots, ({d_{T_1}, \dots}))$.
2. Suppose that $t=|\bigcup_{d\in D}d|$ is the maximum number of vertices protected by any optimal strategy for \CFire.
3. Let $v_t$ be a vertex of maximum distance in $G$ from $r$, which is defended at time $t$.
4. Since the strategy is optimal, there exists an induced path $P$ between $r$ and $v_t$ such that all vertices on $P$ except $v_t$ burn.
5. Let $P$ be a shortest path with this property.
6. given (certain restrictions and lemma) optimal strategy always defends beside fire
7. If $P$ contains fewer than $|D|+1$ vertices,  $v_t$ would burn before it could be protected.
**Conclusion:** $t\leq \ell - 1$.

-----
 
**Consider:**


**Source:** 


**Reference:** 
