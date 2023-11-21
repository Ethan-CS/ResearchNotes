Tags : #cfire #poly-time
Zettel :  20231121-0954
Status : #triage 

-----

# Possible poly-time CFire restrictions

**Previous note:** [[202311210945 Reduction - CFire from Knapsack]]

-----

### Questions & thoughts:

1. Trees of bounded degree: If the graph $G$ is a tree of maximum degree $\Delta$, then CFire is solvable in $O(n\Delta b)$ time using dynamic programming, where $n$ is the number of vertices in $G$ and $b$ is the budget. 
Specifically, we can compute, for each vertex $v$ and each budget $b$, the minimum number of vertices that can be saved if we only defend vertices in the subtree rooted at $v$ and have a budget of at most $b$ by considering two cases: either defend $v$ and its children or don't defend v. The base case is when $v$ is a leaf, where the minimum number of saved vertices is either 0 or 1, depending on whether $v$ is defended or not. The final answer is the minimum number of saved vertices at the root with budget at most $b$ and at least $k$.
2. Planar graphs: If the graph $G$ is planar, then CFire can be solved in $O(n^2 \sqrt{b})$ time using a variant of dynamic programming called the planar separator theorem. 
Specifically, we can compute, for each vertex $v$ and each budget $b$, the minimum number of vertices that can be saved if we only defend vertices in the subgraph of $G$ that is separated from $v$ by a planar separator of size at most $\sqrt{b}$. This can be done by recursively applying the planar separator theorem to the subgraphs on either side of the separator. The base case is when the subgraph has at most one vertex, where the minimum number of saved vertices is either 0 or 1 depending on whether the vertex is defended or not. The final answer is the minimum number of saved vertices at the root with budget at most $b$ and at least $k$. 
3. Bipartite graphs: If the graph $G$ is bipartite, then CFire can be solved in $O(n^3 \ln{b})$ time using a flow-based algorithm. 
Specifically, we can construct a flow network where each vertex $v$ is split into two nodes $v_\textrm{in}$ and $v_\textrm{out}$, and there is an edge from $v_\textrm{in}$ to $v_\textrm{out}$ with capacity $c(v)$ for each vertex $v$. We also add a source node $s$ with an edge of infinite capacity to each vertex $v_\textrm{in}$, and a sink node $t$ with an edge of infinite capacity from each vertex $v_\textrm{out}$. The goal is to find a flow of value at least $k$ from $s$ to $t$ that respects the capacity constraints. Using the max-flow min-cut theorem, the maximum flow is equal to the minimum capacity of any cut that separates $s$ from $t$. In this case, the minimum cut corresponds to a set of defended vertices whose cost is at most the protection budget $b$. Therefore, we can binary search on the value of the minimum cut to find the smallest cut that separates $s$ from $t$ and has cost at most $b$, and check if it has value at least $k$. The binary search takes $O(\ln{b})$ iterations, and each iteration involves computing a max-flow, which can be done in $O(n^3)$ time using the Edmonds-Karp algorithm.

-----
 
