
Tags : #cfire #dynamic-program 
Zettel :  20231121-1003
Status : #triage 

-----

# DP for CFire on Trees of Bounded Degree

**Previous note:** [[202311210954 Possible poly-time CFire restrictions]]

-----

### Questions & thoughts:

Define a function $f(v, b)$ as minimum number of vertices that can be saved if we only defend vertices in the subtree rooted at $v$ and we have a budget of at most $b$. 
We can compute this function using the following recurrence: 
$f(v, b) = min{f(u, b - c(v)) + 1} \texmrm{ if } b >= c(v)$,
where the minimum is taken over all children u of v, and c(v) is the cost of defending vertex v. The base case is when v is a leaf, in which case f(v, b) is either 0 or 1, depending on whether v is defended or not. The final answer is the minimum number of saved vertices at the root with budget at most b and at least k. To see why this recurrence works, consider a vertex v and a budget b. If we don't defend v, then the minimum number of saved vertices is equal to the sum of the minimum number of saved vertices in each subtree rooted at v's children, since we can't save any vertices in v's subtree. If we do defend v, then we have to subtract the cost of defending v from the budget, and the minimum number of saved vertices is equal to the sum of the minimum number of saved vertices in each subtree rooted at v's children, plus 1 for v itself. We take the minimum of these two cases to get the minimum number of saved vertices for v and b. We can compute f(v, b) for all vertices v and budgets b using a bottom-up dynamic programming approach, starting from the leaves and working our way up to the root. The time complexity of this approach is O(n*d*b), where n is the number of vertices in the tree, d is the maximum degree of the tree, and b is the maximum budget. This is because we need to compute f(v, b) for each vertex v and each budget b, and there are at most n*d such pairs.

-----
 
