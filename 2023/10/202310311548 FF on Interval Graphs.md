Tags : #Firefighter #interval 
Zettel :  20231031-1548
Status : #triage 

-----

# Firefighting on Interval Graphs

**Previous note:** [[202310311347 Trying CFire number defended again]]

-----

### Questions & thoughts:

**Lemma 9:**[^1] _Let_ $(G, r)$ _be an instance of_ Firefighter Reserve Deployment _such that $G$ is an AT-free graph. For any minimal strategy for the Firefighting-with-Reserve game on_ $(G, r)$, the last line of defence is the union of at most two minimal separators of $G$._

**Proof.**
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

**Lemma 10:**[^1] Let $(G,s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. Consider any strategy for the Firefighting-with-Reserve game on $(G, s)$. At the start of time step $t \geq 1$, let $u$ denote the leftmost burning vertex and let $v$ denote the rightmost burning vertex. Then every vertex $w$ with $r(u) < l(w) < r(w) < l(v)$ is either burning or protected. Moreover, any vertex that neighbours a burning vertex and that is neither burning nor protected at the start of time step $t$ is in $N(u) \cup N(v)$.

**Lemma 11:**[^1] Let $(G,s)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. Let $F_1, \dots, F_k$ be an optimal strategy for the Firefighting-with-Reserve game on $(G, s)$. At the start of time step $t\geq 1$, let $v$ denote the rightmost burning vertex. Let $Y$ denote the set of vertices in $\bigcup^t_{i=1} Fi$ that neighbour $v$ and do not neighbour any burning vertex in time step $t − 1,...,0$. Then $F_1^\prime,\dots,F_k^\prime$ is also an optimal strategy for the Firefighting-with-Reserve game on $(G,s)$, where $F_i^\prime=F_i \setminus Y$ for all $i\neq t$ and $F_t^\prime$ consists of $F_t\setminus Y$ and the $|Y|$ rightmost intervals that are unburned at the start of time step $t$ and that intersect $v$.

**(Previous) Corollary 3:**[^1] Let $(G, s)$ be an instance of Firefighter Reserve Deployment. There exists an optimal strategy for the Firefighting-with- Reserve game on $(G , s)$ that only protects vertices that neighbour a vertex that is on fire.

**Original Corollary (of Lemmas 10 & 11 and Corollary 3):**[^1] Let $(G, r)$ be an instance of Firefighter Reserve Deployment such that $G$ is an interval graph. There is an optimal strategy for this problem that, for $u$ and $v$ the left- and right-most burning vertices at the start of timestep $t\geq 1$, in each timestep protects the $f_l$ leftmost vertices that neighbour $u$ and $f_r$ rightmost vertices that neighbour $v$ for an appropriate choice of $f_l$ and $f_r$.

**Original Theorem:**[^1] Firefighter can be solved in time $O(n^7)$ on interval graphs on $n$ vertices.

**Proof.**
Let ($G,s)$ be an instance of Firefighter such that $G$ is an interval graph on $n$ vertices. Instead of solving Firefighter on $(G , s)$, we solve Firefighter Reserve Deployment on $(G , s)$, which is equivalent according to (another previous lemma).

Consider the following table: $A(s_l,s_r,u_l,u_r,f)$ is the max. number of vertices that can be protected if:
 - $s_l$ is the leftmost interval that is on fire, 
 - $s_r$ is the rightmost interval that is on fire,
 - $u_l$ is the rightmost interval not ending to the right of the right endpoint of $s_l$ that is unburned and unprotected, 
 - $u_r$ is the leftmost interval not ending to the left of the left endpoint of $s_r$ that is unburned and unprotected, and 
 - $f$ is the size of the reserve. 
We also allow $u_l$ and $u_r$ to be the special symbol \ to signify that the fire is contained on the left respectively the right side of the graph. If ul ̸=⊥̸= ur , then we set

A(sl,sr,ul,ur,f)= max {fl+fr+A(sl′,sr′,ul′,ur′,f−fl−fr+1)}. fl,fr≥0

fl+fr≤f

In the formula, sl′ is the (fl +1)-th leftmost unburned interval intersecting the left endpoint of sl. This interval can be computed from ul. Similarly, sr′ is the (fr +1)-th rightmost unburned interval intersecting the right endpoint of sr, which can be computed from ur. If sl′ does not exist, we set ul′ to ⊥ and sl′ to sl. Otherwise, we set ul′ to the rightmost nonneighbor of sl ending to left of sl. If sr′ does not exist, we set ur′ to ⊥ and sr′ to sr. Otherwise, we set ur′ to the leftmost non-neighbor of sr starting to the right of sr.

If say ul =⊥̸= ur , the formula simplifies to  
A(sl,sr,ul,ur,f)= max{fr+A(sl,sr′,ul,ur′,f−fr+1)},

0≤fr≤f

where the meaning of sr′ and ur′ is the same as before. A similar formula can be given in case ul ̸=⊥=ur. Finally, for any sl,sr, f , we set A(sl,sr,⊥,⊥, f ) to the number of vertices in the connected components of G \(Xl ∪ Xr) that do not contain s, where Xl is the set of vertices intersecting the left endpoint of sl and Xr is the set of vertices intersecting the right endpoint of sr.

We now compute p∗ = A(s,s,ul,ur,1), where ul is the leftmost neighbor of s and ur is the rightmost neighbor of s. Then there is a strategy that saves p∗ vertices of G.

The correctness of the algorithm follows from Lemma 9 and Corollary 12. Since the table A has five indices that each take at most n different values and since an entry of A is a maximum over at most two numbers that each take at most n different values, the algorithm takes O(n7) time. 2



-----
 
**Consider:** how does this translate to CFire?


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)

