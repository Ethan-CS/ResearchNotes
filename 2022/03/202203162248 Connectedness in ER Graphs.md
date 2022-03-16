Tags :
Zettel :  20220316-2248
Status : #triage 

-----

# Connectedness in ER Graphs

**Previous note:** [202203162231 Results so far](202203162231%20Results%20so%20far.md)

-----

### Questions & thoughts:

For some $k\geq 1$ denote by $C_k$ the number of connected components of order $k$ in an Erdos-Renyi random graph $G(n,p)$. We can see that 
$$ 
E(C_1)=n(1-p)^{n-1}.
$$
Now, 
$$n(1-p)^{n-1}\approx n\textrm{e}^{-pn}=\textrm{e}^{\log{(n)}-pn},$$ 
meaning when $p<<\log(n)/n$ we may expect (on average) few isolated vertices. 

Proposition: let $\omega(n)\geq0$ be s.t. $\omega(n)\rightarrow\infty$ and $\omega(n)\leq\log(\log(n)). and $$p(n)$ be $p(n)=(\log(n)-\omega(n))/n.$ Then, $G_{n,p}$ is disconnected with high probability.

(Proof not too difficult - use Chebyshev's Inequality)

-----
 
**Consider:** will "disconnected with high probability" be enough for us to claim this is an upper bound on the probabilities we can use our equation generation procedure on for ER graphs? Or can we show that this will be infeasible in enough places to make this a bad upper bound?


**Source:** _Connected components in Erdos-Renyi random graphs,_ Karen Gunderson, 2013 (lecture notes for the course MATH36201 Complex Networks that Gunderson taught that year at Bristol University, although Gunderson is a big name in this type of work so probably has a paper with these results in too).

