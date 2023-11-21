Tags : #reduction #cfire #knapsack
Zettel :  20231121-0945
Status : #triage 

-----

# CFire NP-hard by reduction from Knapsack

**Previous note:** [[202311160940 Pseudocode for Specific PathContainable Verification]]

-----

### Questions & thoughts:

Given an instance of the KNAPSACK problem with $n$ items of weights $w_1, w_2, ..., w_n$ and values $v_1, v_2, ..., v_n$, we can construct a tree $T$ with $n+1$ vertices as follows: 
 - the root vertex $v_0$ has degree $n$ and is connected to $n$ leaf vertices $v_1, v_2, \dots, v_n$, each of which has weight $w_i$ and value $v_i$. 
 - The protection budget $b$ in the CFire instance is set to the capacity of the knapsack, and the goal is to defend a subset of the leaf vertices with total weight at most $b$ and total value at least $k$.
 - Defend all the leaf vertices whose weights sum up to at most $b$, since this corresponds to the items that can be put in the knapsack by computing, for each vertex $v$ and each budget $b$, the minimum number of vertices that can be saved if we only defend vertices in the subtree rooted at $v$ and have a budget of at most $b$. This can be done using dynamic programming and the final answer is the minimum number of saved vertices.

-----
 