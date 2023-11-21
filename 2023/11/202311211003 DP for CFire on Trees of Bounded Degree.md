
Tags : #cfire #dynamic-program 
Zettel :  20231121-1003
Status : #triage 

-----

# DP for CFire on Trees of Bounded Degree

**Previous note:** [[202311210954 Possible poly-time CFire restrictions]]

-----

### Questions & thoughts:

  
ChatGPT

Find a strategy to defend certain vertices in a tree (to minimise total cost and) ensure that a minimum number of vertices are saved when a fire breaks out.

1. **State:** the state is represented as a tuple $(v, i, d)$ where:
	 - $v$ is the current vertex
	 - $i$ is the timestep, and
	 - $d$ is the number of vertices defended so far.
 2. **Recursive function:** Let $f(v, i, d)$ be the minimum cost to defend $d$ vertices up to time $i$ starting from vertex $v$. The function can be defined as follows:
$$f(v, i, d)=\min_{u \in N(v)}\{f(u, i-1, d^\prime)+c(v) \mid d^\prime \leq d-1\}$$
where $d^\prime$ is the number of vertices defended in the neighbours of $v$ at time $i-1$.
3. **Base case:** when $i=0$, which we take to be before fire breaks out at the root $r$, in which case the cost is zero.
4. **Goal:** find the minimum cost to defend at least $k$ vertices by the end of the process at time $T$. This can be found by iterating over all vertices $v$ and $d$ at time $T$ and selecting the minimum cost such that $d\geq k$.

Time complexity: let $a$ be the average degree of $T$, then the dynamic program is computable in $O(n\cdot T\cdot k\cdot a +n\cdot T \cdot(k+1))=O(a\cdot k\cdot n\cdot T)$ time. $T$ and $a$ are bounded above by $n$, so this becomes $O(kn^3)$ in the worst case.



-----
 
