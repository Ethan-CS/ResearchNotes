Tags :
Zettel :  20250429-1437
Status : #triage 

-----

# Poly time result for InfVax on permutation graphs first attempt

**Previous note:** [[]]

-----

### Questions & thoughts:

**Lemma 1:** In a permutation graph G=(V,E)G=(V,E), there are at most $O(n^2)$ minimal separators, and they are enumerable in polynomial time.

**Proof.** Let $G$ be represented geometrically by line segments between two parallel lines $L1$ and $L2$, with each vertex $v$ corresponding to a segment connecting $(i,0)$ to $(\pi(i),1)$, where $\pi$ is a permutation of ${1,\dots,n}$. A _scanline_ is any vertical line segment between $L_1$ and $L_2$ not intersecting any vertex endpoints [cite](https://research.tue.nl/files/4297898/390171.pdf)[](https://www.sciencedirect.com/science/article/pii/S0304397510003518/pdf?md5=9212f6c98dc2f402a0b7f4766f4bb31d&pid=1-s2.0-S0304397510003518-main.pdf).

For non-adjacent vertices $x$ and $y$, obviously their segments do not cross. A minimal $x,y$-separator $S$ corresponds precisely to the set of segments crossing a scanline placed between $x$ and $y$ [cite](https://research.tue.nl/files/4297898/390171.pdf), because:
1. $S$ must separate $x$ and $y$ into distinct components.
2. In the geometric representation, this separation is achieved by a vertical scanline partitioning the segments into left/right components.
3. All segments crossing this scanline form SS, as their removal disconnects $x$ and $y$ [cite 1](https://research.tue.nl/files/4297898/390171.pdf)[cite 2](https://www.sciencedirect.com/science/article/pii/S0304397510003518/pdf?md5=9212f6c98dc2f402a0b7f4766f4bb31d&pid=1-s2.0-S0304397510003518-main.pdf).
The number of minimal separators is bounded by the number of scanline positions. Each scanline is determined by two pairs of endpoints: one on $L_1$ between $i$ and $i+1$, and one on $L_2$ between $\pi(j)$ and $\pi(j+1)$. There are $O(n^2)$ such positions [cite 1](https://research.tue.nl/files/4297898/390171.pdf)[cite 2](https://www.sciencedirect.com/science/article/pii/S0304397510003518/pdf?md5=9212f6c98dc2f402a0b7f4766f4bb31d&pid=1-s2.0-S0304397510003518-main.pdf). Enumeration involves checking all possible scanlines and recording the crossing segments, achievable in $O(n^3)$ time by iterating over all $O(n^2)$ scanlines and verifying crossings in $O(n)$ time per scanline.

**Lemma 2:** there exists an optimal strategy for InfVax on permutation graphs in which directly defended vertices are subsets of minimal separators.

**Proof.**  Suppose an optimal strategy defends a vertex $v$ not in any minimal separator. Let $t$ be the time step when $v$ is defended. Since $v$ is not in a minimal separator, its removal does not disconnect $G$. However, defending $v$ allows defence to spread to its neighbours. Consider the earliest time $t^\prime\geq t$ when the defence propagates to a vertex $u$ in a minimal separator $S$. Replace the defence of $v$ at time $t$ with a defence of $u$ at $t$. This substitution preserves the defensive spread to $u$ and potentially blocks more fire spread, as $S$ is a bottleneck. By induction, all non-separator defences can be replaced with separator defences without reducing saved vertices [cite 1](https://research.tue.nl/files/4297898/390171.pdf)[cite 2](https://www.sciencedirect.com/science/article/pii/S0304397515010853)[cite 3](https://www.semanticscholar.org/paper/b95375602515336650075b19013b8bfe35a22f3f).

Thus, an optimal strategy exists that only defends vertices from minimal separators. This aligns with the budget-Firefighter approach on permutation graphs, where minimal separators provide critical choke points [cite 1](https://www.sciencedirect.com/science/article/pii/S0304397515010853)[cite 2](https://www.semanticscholar.org/paper/b95375602515336650075b19013b8bfe35a22f3f).


-----
 
**Consider:**


**Source:** 


**Reference:** 
