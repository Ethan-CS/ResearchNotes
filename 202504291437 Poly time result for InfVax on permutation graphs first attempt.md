Tags :
Zettel :  20250429-1437
Status : #triage 

-----

# Poly time result for InfVax on permutation graphs first attempt

**Previous note:** [[]]

-----

### Questions & thoughts:

**Lemma 1:** In a permutation graph G=(V,E)G=(V,E), there are at most $O(n^2)$ minimal separators [(Corollary 3.1, Bodlaender, Kloks, Kratsch 1992)](https://research.tue.nl/files/4297898/390171.pdf), and they are enumerable in polynomial time [(Lem. 3.1, Bodlaender, Kloks, Kratsch 1992)](https://research.tue.nl/files/4297898/390171.pdf)


**Lemma 2:** there exists an optimal strategy for the Infectious Vaccination problem on permutation graphs in which directly defended vertices are subsets of minimal separators.

**Proof.**  Suppose an optimal strategy defends a vertex $v$ not in any minimal separator. Let $t$ be the time step when $v$ is defended. Since $v$ is not in a minimal separator, its removal does not disconnect $G$. However, defending $v$ allows defence to spread to its neighbours. Consider the earliest time $t^\prime\geq t$ when the defence propagates to a vertex $u$ in a minimal separator $S$. Replace the defence of $v$ at time $t$ with a defence of $u$ at $t$. This substitution preserves the defensive spread to $u$ and potentially blocks more fire spread, as $S$ is a 'bottleneck' (define this; can we guarantee/justify this does at least no worse? what if v is adjacent to fire, so by defending u we may not clearly defend at least as many). By induction, all non-separator defences can be replaced with separator defences without reducing saved vertices [(Bodlaender, Kloks, Kratsch 1992), ](https://research.tue.nl/files/4297898/390171.pdf)[(Fomin, Heggernes, Jan van Leeuwen 2016).](https://www.sciencedirect.com/science/article/pii/S0304397515010853) (need to explain this better). Thus, an optimal strategy exists that only defends vertices from minimal separators (is this sufficient to show this?).

**Proof (2nd attempt).** Let $G$ be a permutation graph and $S$ be the set of all minimal separators of $G$. Assume we have an optimal strategy $\sigma$ for InfVax on $G$ that defends a vertex $v$ that is not in any set in $S$. We construct a modified strategy $\sigma^\prime$ by replacing $v$ with a vertex $u$ that is in a minimal separator and claim our construction preserves optimality.
(Base case). If no non-separator vertex is defended, i.e. no such $v$ exists, the claim is trivially true.
(Inductive hypothesis) Assume that all strategies with $k$ non-separator defences can be replaced.
()


**Theorem.** InfVax on permutation graphs is polynomial-time solvable.

**Proof.** Let $G=(V, E)$ be a permutation graph rooted at $r$, $b\in\mathbb{N}$ be the budget and $S$ be the set of all minimal separators in $G$. By Lemma 1, $S$ is of size polynomial in the size of $G$ and can be enumerated in polynomial time also in the size of $G$. In turn $t$ (an integer between 0 and $|V|$), let $B_t$ be the set of burning vertices in turn $t$ and $D_t$ be the set of defended vertices in turn $t$. Let $V(t, B_t, D_t)$ be the maximum number of vertices that can be saved, from state $(t, B_t, D_t)$.
 - Initially, $B_0=\{r\}$ and $D_0=\emptyset$.
 - For each time step $t=1, 2, \dots, n$:
	 - for each subset $S^\prime\subseteq S$ such that $|S^\prime|\leq b$ and $S^\prime\cap(B_{t-1}\cup D_{t-1})=\emptyset$:
		 - compute $B_t$ and $D_t$ after defending $S^\prime$ by:
			 - initially, set $D_t=D_{t-1}\cup S^\prime$ and $B_t=B_{t-1}$
			 - defence spread: add all vertices $v\in V\setminus (B_{t-1}\cup D_t)$ with a neighbour in $D_{t-1}$ to $D_t$ 
			 - fire spread: add all vertices $v\in V\setminus (B_t\cup D_t)$ with a neighbour in $B_{t-1}$ to $B_t$
		 - update $V(t, B_t, D_t)$
 There are at most $O(n^2)$ minimal separators and they can be enumerated in $O(n^3)$ time by lemma 1. There are $O(n)$ time steps; at each time step, there are $O(|S|^b)=O(n^{2b})$ choices for potential defence. Each state $B$ and $D$ have $O(2^n)$ possible combinations in general, but we bound burning and defence fronts by $O(n^2)$ by lemma 2, avoiding enumerating all of these states. Hence the total runtime: states $O(n^{2b+3})$, per-state processing $O(n)$ (defence and fire spread), so overall $O(n^{2b+4})$.

-----
 
**Consider:**


**Source:** 


**Reference:** 
