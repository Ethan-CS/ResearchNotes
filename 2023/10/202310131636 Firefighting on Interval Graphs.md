Tags :
Zettel :  20231013-1636
Status : #triage 

-----

# Firefighting on Interval Graphs

**Previous note:** [[202309201616 Equations output for pseudocode]]

-----

### Questions & thoughts:

Firefighting is poly. time solvable on interval graphs [^1]. We conjecture that our cost-function variations are *not* poly. time solvable on interval graphs. The original proof is sketched below:

**Definition:** Three vertices of a graph form an **asteroidal triple** if every two of them are connected by a path avoiding the neighbourhood of the third. A graph is **AT-free** if it does not contain any asteroidal triple.

**Lemma:** Let $(G, r)$ be an instance of Firefighter such that $G$ is an AT-free graph. For any minimal strategy for the Firefighting-with-Reserve game on $(G,r)$, the last line of defence is the union of at most two minimal separators of $G$.

Proof. Let $R$ be the set of vertices rescued by the strategy, let $R_1,\dots,R_p$ denote the connected components of $G[R]$ and let $B_P$ denote the set of vertices that either burn or are protected. Observe that $B_P$ is connected, or the strategy would not be minimal. Moreover, $R_1,\dots,R_p$ are connected components of $G[V(G)\setminus B_P]$; hence, $N(R_i)$ is a minimal separator of $G$ for each $i\in\{1,\dots,p\}$. Now consider the partial order that is induced on $\{N(R_i)\}^p_{i=1}$ by the inclusion-relation, and let $I \subseteq \{1,\dots, p\}$ be the set of indices corresponding to the maximal elements of this relation. Then the elements of ${N(R_i)}_{i\in I}$ are minimal separators that are incomparable with respect to set inclusion. 

Moreover, for each $j \in I$, the component of $G−N(R)$ that is not equal to $R$ contains $B_P$, and thus in particular it contains $(\bigcup_{i\in I} N(R_i))\setminus N(R_i)$. Combined with the assumption that $G$ is AT-free, it then follows from Broersma et al. [Definition 1, 18; Lemma 20](https://doi.org/10.1007/s00453-001-0091-x) that $|I|\leq 2$. Hence, as $\displaystyle N(R)=\bigcup^p_{i=1} N(R_i)=\bigcup_{i\in I}N(R_i)$, the lemma follows.


-----
 
**Consider:**


**Source:** 

[1]: Fedor V. Fomin, Pinar Heggernes, Erik Jan van Leeuwen, *The Firefighter problem on graph classes,* Theoretical Computer Science, Volume 613 (2016), pp. 38-50, ISSN 0304-3975, [doi](https://doi.org/10.1016/j.tcs.2015.11.024)




**Reference:** 
