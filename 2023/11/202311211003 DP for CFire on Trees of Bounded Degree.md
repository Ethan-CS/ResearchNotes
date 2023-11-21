
Tags : #cfire #dynamic-program 
Zettel :  20231121-1003
Status : #triage 

-----

# DP for CFire on Trees of Bounded Degree

**Previous note:** [[202311210954 Possible poly-time CFire restrictions]]

-----

### Questions & thoughts:

1. **Initialisation:**
    - Initialise DP table to store minimum costs and strategy table to track defense strategies.
    - Set initial costs in the DP table to infinity and initialize strategies as empty lists.
2. **Base Case:**
    - Set the base case for the root vertex, where defending zero vertices incurs zero cost.
    - Initialise the strategy for the root vertex as an empty list.
3. **Recursive DP:**
    - For each defence level, each vertex, and each neighbouring vertex:
        - Calculate the cost of defending the current vertex considering the strategy from the neighbouring vertex.
        - Update DP table and strategy table if the new cost is smaller than the existing cost.
4. **Minimum Cost Retrieval:**
    - Find the minimum cost among all non-root vertices and defense levels.
    - Retrieve the defence strategy associated with the minimum cost.
5. **Budget Check:**
    - Check if the minimum cost is within the given budget.
        - If yes, return the defence strategy.
        - If no, return an empty list.


-----
 
