Tags :
Zettel :  20240116-1332
Status : #triage 

-----

# CFire on Spider Graphs

**Previous note:** [[202311301441 Random Access for MCMC Simulation]]

-----

### Questions & thoughts:

Below: short section removed from current overleaf doc. on cost function firefighting.

Next, we introduce a new graph class - the spider graph.We show that \Fire is solvable in time polynomial in the size of the input when restricted to these graphs before showing that \CFire with temporal cost functions remains NP-hard (and complete) on inputs restricted to the same graph class.

**Definition.** *A spider graph is a tree with one vertex of degree three or more, all others having degree at most two.*

**Theorem.** *The Firefighter Problem is solvable in time polynomial in the size of the input when restricted to spider graphs.*

*Proof.* First, consider the case of fire breaking out on a path extending from the central vertex of the spider. Defend the vertex adjacent to the fire closest to the central vertex on the first time-step. In the second time-step, defend the only other vertex adjacent to fire (if such a vertex exists i.e., the fire did not start on a leaf of a path or on a fire adjacent to a leaf). The fire is contained in constant time.
    
Consider the case of fire breaking out at the central vertex of the spider. Let $p$ be the number of paths extending from the central vertex. Find the length of all $p$ paths in $O(n)$-time and order the paths by decreasing length in $O(n\log(n))$-time (in the worst case). Then, defend the $i$-th vertex on each path at time-step $i$ while possible (i.e., until the shorter paths have entirely burned or the fire is contained) in $O(p)$-time. This procedure takes place in $O(n\log(n))$-time in the worst case, i.e., it takes time that is polynomial in the size of the input and clearly allows the fewest possible vertices to burn. $\square$ 


**Theorem.** CFire is NP-complete even for instances restricted to spiders graphs.

*Proof.* We reduce from Temporal Knapsack. Consider an arbitrary instance of TKnap on: a lifetime $T\in\mathbb{N}$; a set of items $I$ where each item $i$ has a value $\psi_i$, weight $\omega_i$ and active time series $T\subseteq\mathbb{N}^T$; a desired value $x\in\mathbb{N}$; and set of maximum weight capacities $W$ for each time-step up to $T$. We construct an instance of CFire as follows. Construct a graph $G=(V, E)$ by creating, for each item $i\in I$, a path of length $\psi_i$. Connect one end of each path to a vertex $c$. This clearly creates a spider with central vertex $c$ connected to $|I|$ paths. Define a cost function $c:V\times\mathbb{N}$ as follows. Let the cost of the central vertex and all other vertices not adjacent to the central vertex as $(\sum_w\in W w)+1$. Let the cost of defending any vertex adjacent to the central vertex to be the weight of the item from which it was taken. Let the per-time budget be the per-time weight capacity. $\square$

Hence, we have shown that CFire with temporal cost functions remains NP-hard on a graph class (spiders) on which instances of Fire are solvable in time polynomial in the size of the instance.

-----
