
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
$f(v, b) = \displaystyle\min_{u\in V(T[v])}\{f(u, b - c(v)) + 1\} \textrm{ if } b \geq c(v)$
where the minimum is taken over all children $u$ of $v$, and $c(v)$ is the cost of defending vertex $v$. 

Base case: when $v$ is a leaf, when $f(v, b)$ is either 0 or 1 depending on whether v is defended or not. 
Final answer: minimum number of saved vertices with budget at most $b$ and at least $k$.

To see why this recurrence works, consider a vertex $v$ and a budget $b$. 
 - If we don't defend $v$, the minimum number of saved vertices is equal to the sum of the minimum number of saved vertices in each subtree rooted at the children of $v$, since we can't save any vertices in the subtree rooted at $v$.
 - If we do defend $v$, we subtract the cost of defending $v$ from the budget and the minimum number of saved vertices is equal to the sum of the minimum number of saved vertices in each subtree rooted at the children of $v$ (plus 1 for $v$ itself).
 - We take the minimum of these two cases to get the minimum number of saved vertices for $v$ and $b$. We can compute $f(v, b)$ for all vertices $v$ and budgets $b$ using a bottom-up dynamic programming approach, starting from the leaves and working our way up to the root. 
 - The time complexity of this approach is $O(n \Delta b)$, where $n$ is the number of vertices in the tree, $\Delta$ is the maximum degree of the tree and $b$ is the maximum budget per turn. This is because we need to compute $f(v, b)$ for each vertex $v$ and each budget $b$, and there are at most $nd$ such pairs.


Input: A tree $T$ of maximum degree $\Delta$, a protection budget $b$, and a minimum number of saved vertices $k$. 

Output: The minimum number of saved vertices in $T$ with budget at most $b$ and at least $k$. 
1. Initialise $f(v, b)=\infty$ for all vertices $v\in V(T)$ and budgets $b$.
2. For each leaf vertex $v$, set $f(v, c(v))=1$ if $c(v) \leq b$ and 0 otherwise.
3. For each non-leaf vertex v, compute f(v, b) using the recurrence f(v, b) = min{f(u, b - c(v)) + 1} if b >= c(v), where the minimum is taken over all children u of v.
4. Compute the minimum number of saved vertices at the root with budget at most b and at least k as min{f(root, b) : f(root, b) >= k}.

-----
 
