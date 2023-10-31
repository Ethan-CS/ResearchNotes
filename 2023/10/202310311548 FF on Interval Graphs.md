Tags : #Firefighter #interval 
Zettel :  20231031-1548
Status : #triage 

-----

# Firefighting on Interval Graphs

**Previous note:** [[202310311347 Trying CFire number defended again]]

-----

### Questions & thoughts:

*Throughout, let $(G,s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph.*

**Original lemma 9:**[^1] _Let_ $(G, r)$ _be an instance of_ Firefighter Reserve Deployment _such that $G$ is an AT-free graph. For any minimal strategy for the Firefighting-with-Reserve game on_ $(G, r)$, the last line of defence is the union of at most two minimal separators of $G$._

Original proof.
1. Let:
	 - $R$ denote the set of vertices rescued by the strategy 
	 - $R_1, \dots, R_p$ denote the connected components of $R$,
	 - $BP$ denote the set of vertices that either burn or are protected. 
2. Observe that $BP$ is connected, else strategy is not minimal. 
3. Observe $R_1, \dots, R_p$  are connected components of $G[V(G)\setminus BP]$
Conclusion 1: $N(R_i)$ is a minimal separator of $G$ for each $i\in\{1, \dots, p\}$
4. Consider the partial order that is induced on  by the inclusion-relation
5. Let $i\subseteq\{1, \dots, p\}$ be the set of indices corresponding to the maximal elements of this relation. 
6. Notice the elements of $\{N(R_i)\}_{i\in I}$ are minimal separators that are incomparable with respect to set inclusion. 
7. For each $j\in I$, the component of $G-N(R_j)$ not equal to $R_j$ contains BP, and thus in particular it contains $(\bigcup_{i\in I}N(R_i))\setminus N(R_j)$
8. Combined with the assumption that _G_ is AT-free, it then follows from [Broersma et al. Lemma 20](https://www.sciencedirect.com/science/article/pii/S0304397515010853#br0200) that $|I|\leq2$.
Conclusion: As $N(R)=\bigcup_{i=1}^pN(R_i)=\bigcup_{i\in I}N(R_i)$, the lemma follows. 

Then, we use two lemmas and a previous corollary to give Corollary B.

**Lemma 10:**[^1] Let $(G , s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. Consider any strategy for the Firefighting-with-Reserve game on $(G, s)$. At the start of time step $t \geq 1$, let $u$ denote the leftmost burning vertex and let $v$ denote the rightmost burning vertex. Then every vertex $w$ with $r(u) < l(w) < r(w) < l(v)$ is either burning or protected. Moreover, any vertex that neighbors a burning vertex and that is neither burning nor protected at the start of time step $t$ is in $N(u) \cup N(v)$.

**Lemma 11:**[^1] Let F1,...,Fk be an optimal strategy for the Firefighting-with-Reserve game on (G, s). At the start of time step t ≥ 1, let v denote the rightmost burning vertex. Let Y denote the set of vertices in ti=1 Fi that neighbor v and do not neighbor any burning vertex in time step t − 1,...,0. Then F1′,...,Fk′ isalsoanoptimalstrategyfortheFirefighting-with-Reservegameon(G,s),where Fi′=Fi \Y foralli̸=t,and Ft′ consists of Ft \ Y and the |Y | rightmost intervals that are unburned at the start of time step t and that intersect v.

**Original Corollary**[^1] Let $(G, r)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. There is an optimal strategy for this problem that, for $u$ and $v$ the left- and right-most burning vertices at the start of timestep $t\geq 1$, in each timestep protects the $f_l$ leftmost vertices that neighbour $u$ and $f_r$ rightmost vertices that neighbour $v$ for an appropriate choice of $f_l$ and $f_r$.

All this is used in the proof of the following, which is a dynamic programming approach.

**Original Theorem:**[^1] Firefighter can be solved in time $O(n^7)$ on interval graphs on $n$ vertices.



-----
 
**Consider:** how does this translate to CFire?


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)

