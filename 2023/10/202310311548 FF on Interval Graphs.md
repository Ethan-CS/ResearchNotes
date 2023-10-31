Tags : #Firefighter #interval 
Zettel :  20231031-1548
Status : #triage 

-----

# Firefighting on Interval Graphs

**Previous note:** [[202310311347 Trying CFire number defended again]]

-----

## High-level overview

 - Lemma 9 and Corollary 12 give correctness of algorithm in Theorem 13.
 - Lemma 2 is used to give corollary 3 and so FF and FWR can be used interchangeably where convenient.
 - Lemma 10, lemma 11 and corollary 3 combined give corollary 12.



-----


This lemma is used to prove correctness of a DP algorithm in Theorem 13.

***Lemma 9:**[^1] Let $(G, r)$ be an instance of Firefighter Reserve Deployment such that $G$ is an AT-free graph. For any minimal strategy for the Firefighting-with-Reserve game on $(G, r)$, the last line of defence is the union of at most two minimal separators of $G$.*

**Proof.**
1. Let:
	 - $R$ denote the set of vertices rescued by the strategy 
	 - $R_1, \dots, R_p$ denote the connected components of $R$,
	 - $BP$ denote the set of vertices that either burn or are protected. 
2. Observe that $BP$ is connected, else strategy is not minimal. 
3. Observe $R_1, \dots, R_p$  are connected components of $G[V(G)\setminus BP]$
**C1:** $N(R_i)$ is a minimal separator of $G$ for each $i\in\{1, \dots, p\}$
4. Consider the partial order that is induced on  by the inclusion-relation
5. Let $i\subseteq\{1, \dots, p\}$ be the set of indices corresponding to the maximal elements of this relation. 
6. Notice the elements of $\{N(R_i)\}_{i\in I}$ are minimal separators that are incomparable with respect to set inclusion. 
7. For each $j\in I$, the component of $G-N(R_j)$ not equal to $R_j$ contains BP, and thus in particular it contains $(\bigcup_{i\in I}N(R_i))\setminus N(R_j)$
8. Combined with the assumption that _G_ is AT-free, it then follows from [Broersma et al. Lemma 20](https://www.sciencedirect.com/science/article/pii/S0304397515010853#br0200) that $|I|\leq2$.
Conclusion: As $N(R)=\bigcup_{i=1}^pN(R_i)=\bigcup_{i\in I}N(R_i)$, the lemma follows. $\blacksquare$

-----

***Lemma 10:**[^1] Let $(G,s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. Consider any strategy for the Firefighting-with-Reserve game on $(G, s)$. At the start of time step $t \geq 1$, let $u$ denote the leftmost burning vertex and let $v$ denote the rightmost burning vertex. Then every vertex $w$ with $r(u) < l(w) < r(w) < l(v)$ is either burning or protected. Moreover, any vertex that neighbours a burning vertex and that is neither burning nor protected at the start of time step $t$ is in $N(u) \cup N(v)$.

**Proof** (induction).
1. The statement is true at time step $t = 1$, because $u = v = s$ so there is no vertex $w$ satisfying $r(s) < l(w) < r(w) < l(s)$. 
2. Assume the statement is true at the start of time step $t − 1$: 
	 - Let $u^\prime$ and $v^\prime$ denote the leftmost and rightmost vertices respectively that are burning at the start of time step $t − 1$
	 - Let $u$ and $v$ denote the leftmost and rightmost vertices respectively that are burning at the start of time step $t$. 
3. By the induction hypothesis, all vertices that start burning in time step $t − 1$ neighbour $u^\prime$ or $v^\prime$ hence:
	- $u$ is the leftmost unprotected neighbour of $u^\prime$ (else $u = u^\prime$)
	- $v$ is the rightmost unprotected neighbour of $v^\prime$ (else $v = v^\prime$)
4. Note that any vertex $w$ that satisfies $r(u) < l(w) < r(w) < l(v)$ also satisfies 
	$(r(u^\prime) < l(w) < r(w) < l(v^\prime))$ or $((u) < l(w) < r(u′))$ or $(l(v′)<r(w)<l(v))$
5. In the first case, by induction $w$ is still either burning or protected at the start of time step$ t$.
6. In the second and third cases, since $u$ is a neighbour of $u^\prime$ (or $u=u^\prime$) and $v$ is a neighbour of $v′$ (or $v=v^\prime$), $w$ is a neighbour of $u^\prime$ or of $v^\prime$ respectively, thus $w$ is burning or protected at the start of time step $t$. 
7. Therefore, any vertex $x$ that neighbours a burning vertex and that is neither burning nor protected at time step $t$ satisfies $l(x) < r(u)$ or $l(v) < r(x)$. 
**C:** Since $u$ and $v$ are the leftmost and rightmost vertex respectively that burns at time step $t$, $x$ neighbours $u$ or $v$.

-----

***Lemma 11:**[^1] Let $(G,s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. Let $F_1, \dots, F_k$ be an optimal strategy for the Firefighting-with-Reserve game on $(G, s)$. At the start of time step $t\geq 1$, let $v$ denote the rightmost burning vertex. Let $Y$ denote the set of vertices in $\bigcup^t_{i=1} Fi$ that neighbour $v$ and do not neighbour any burning vertex in time step $t − 1,...,0$. Then $F_1^\prime,\dots,F_k^\prime$ is also an optimal strategy for the Firefighting-with-Reserve game on $(G,s)$, where $F_i^\prime=F_i \setminus Y$ for all $i\neq t$ and $F_t^\prime$ consists of $F_t\setminus Y$ and the $|Y|$ rightmost intervals that are unburned at the start of time step $t$ and that intersect $v$.*

-----

***(Earlier) Lemma 2:** The Firefighter and the Firefighter Reserve Deployment problem are equivalent.*  

**Proof.** 
 1. Consider a strategy $v_1,\dots,v_k$ for the Firefighting game.
 2. At time step t, if the fire reaches vertices $F_t \subseteq \{v_1,\dots,v_k\}$ at time step $t +1$ in $G-\bigcup_{i=1}^{t−1}F_i$, deploy the firefighters in $F_t$ at time $t$. 
**C1:** Because $v_1,\dots,v_k$ is a valid strategy, this must also be a valid strategy. 
**C2:** this new strategy saves exactly the same set of vertices.  
3. Consider a strategy $F_1,\dots,F_k$ for the Firefighting-with-Reserve game. 
4. Consider any ordering $v_1,\dots,v_k^\prime$ of the vertices in $F_1,...,F_k$ such that $v_a \in F_i, v_b \in F_j$ for $i< j$ implies $a<b$. 
**C1:** Because $F_1,\dots,F_k$ is a valid strategy, this ordering is also a valid strategy. 
**C2:** this new strategy saves exactly the same set of vertices.  
**C:** Firefighter and Firefighter-Reserve-Deployment are equivalent problems. $\blacksquare$

Consider the two transformations in the above proof. If we apply the second transformation on a strategy for the Firefighting-with-Reserve game, and then the first, we obtain a strategy for the Firefighting-with-Reserve game with the following property.

***(Earlier) Corollary 3 (of Lemma 2):**[^1] Let $(G, s)$ be an instance of Firefighter Reserve Deployment. There exists an optimal strategy for the Firefighting-with- Reserve game on $(G , s)$ that only protects vertices that neighbour a vertex that is on fire.*

-----

***Original Corollary (of Lemmas 10 & 11 and Corollary 3):**[^1] Let $(G, r)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. There is an optimal strategy for this problem that, for $u$ and $v$ the left- and right-most burning vertices at the start of timestep $t\geq 1$, in each timestep protects the $f_l$ leftmost vertices that neighbour $u$ and $f_r$ rightmost vertices that neighbour $v$ for an appropriate choice of $f_l$ and $f_r$.*

-----

***Theorem 13:**[^1] Firefighter can be solved in time $O(n^7)$ on interval graphs on $n$ vertices.*

**Proof.**
Let ($G,s)$ be an instance of Firefighter such that $G$ is an interval graph on $n$ vertices. Instead of solving Firefighter on $(G , s)$, we solve Firefighter Reserve Deployment on $(G , s)$, which is equivalent according to (another previous lemma).

Consider the following table: $A(s_l,s_r,u_l,u_r,f)$ is the max. number of vertices that can be protected if:
 - $s_l$ is the leftmost interval that is on fire, 
 - $s_r$ is the rightmost interval that is on fire,
 - $u_l$ is the rightmost interval not ending to the right of the right endpoint of $s_l$ that is unburned and unprotected, 
 - $u_r$ is the leftmost interval not ending to the left of the left endpoint of $s_r$ that is unburned and unprotected, and 
 - $f$ is the size of the reserve. 
We also allow $u_l$ and $u_r$ to be the special symbol $\perp$ to signify that the fire is contained on the left or right side of the graph respectively.

If $u_l \neq\perp = u_r$ , then we set

$A(s_l,s_r,u_l,u_r,f)= \displaystyle\textrm{max}_{fl,fr≥0, fl+fr≤f} \{f_l+f_r+A(s_l^\prime,sr^\prime,ul^\prime,ur^\prime,f−f_l−f_r+1)\}$

In the formula:
 - $s_l^\prime$ is the $(f_l +1$)-th leftmost unburned interval intersecting the left endpoint of $s_l$. 
	 - This interval can be computed from $u_l$.
 - Similarly, $s_r^\prime$ is the $(f_r +1)$-th rightmost unburned interval intersecting the right endpoint of sr, which can be computed from ur. 
 - If $s_l^\prime$ does not exist, we set $u_l^\prime=\perp$ and $s_l^\prime=s_l$. 
 - Otherwise, we set $u_l^\prime$ to the rightmost non-neighbour of $s_l$ ending to left of $s_l$. 
 - If $s_r^\prime$ does not exist, we set $u_r^\prime=\perp$ and $s_r^\prime=s_r$. 
 - Otherwise, we set $u_r^\prime$ to the leftmost non-neighbour of $s_r$ starting to the right of $s_r$.

If say $u_l =\perp\neq ur$ , the formula simplifies to  
$A(s_l,s_r,u_l,u_r,f)= \textrm{max}_{0≤f_r≤f}\{f_r+A(s_l,s_r^\prime,u_l,u_r^\prime,f−f_r+1)\}$
where the meaning of $s_r^\prime$ and $u_r^\prime$ is the same as before. 
 
 - Finally, for any $s_l, s_r, f $, we set $A(s_l, s_r, \perp, \perp, f)$ to the number of vertices in the connected components of $G \setminus(X_l \cup X_r)$ that do not contain $s$, where $X_l$ is the set of vertices intersecting the left endpoint of $s_l$ and $X_r$ is the set of vertices intersecting the right endpoint of $s_r$.

 - We now compute $p^∗=A(s,s,u_l,u_r,1)$, where $u_l$ is the leftmost neighbour of $s$ and $u_r$ is the rightmost neighbour of $s$. Then there is a strategy that saves $p^∗$ vertices of $G$.

 - The correctness of the algorithm follows from Lemma 9 and Corollary 12. 
 - Since the table $A$ has five indices that each take at most $n$ different values and since an entry of $A$ is a maximum over at most two numbers that each take at most $n$ different values, the algorithm takes $O(n7)$ time. $\blacksquare$

-----
 
**Consider:** how does this translate to CFire?


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)

