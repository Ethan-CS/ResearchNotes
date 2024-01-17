Tags :
Zettel :  20240117-1036
Status : #triage 

-----

# With-reserve 'equivalence'

**Previous note:** [[]]

-----

### Questions & thoughts:

Another cut - with-reserve problem equivalence. Jess and I don't think this works in the way we need it to without extra conditions!

It is sometimes convenient to permit the `rolling over' of unused budget when considering strategies for \Fire variants, which gives rise to a new but equivalent problem called Firefighter-with-Reserve (\FRes).
For example, consider an instance of \FRes in which each budget at each turn is 1. At time $t=0$, the defender can deploy one defence. If they choose not to, at time $t=1$ they have a new defence to make and so up to two defences can now be implemented (or rolled over to $t=2$). It is shown in \cite{fomin_2016} that \Fire and \FRes are equivalent.
We define the Cost Function Firefighter-with-Reserve problem (\CFRes) as \FRes with a cost to defend each vertex and an integer budget (rather than just one) added to the reserve per turn and show that \bFire and \bFRes are equivalent.

\begin{definition}[Decision Problem Equivalence]\todo{write this}
\end{definition}

\begin{theorem}\label{prop:cfire-cfres-equiv}
    \CFire and \CFRes are equivalent problems.
\end{theorem}
\begin{proof}
    This follows a similar structure to the proof of the analogous result for \Fire and \FRes equivalency in \cite{fomin_2016}. Let $\rho=\{\rho_1, \rho_2, \dots, \rho_k\}$ where $\rho_i=(\rho_i^1,\dots,\rho_i^b)$ be a valid strategy for an arbitrary instance of \CFire and consider an instance of \CFRes with the same rooted graph, budget and integer $k$. Construct a strategy $\sigma$ as follows: suppose that at time $t=i+1$, the fire spreads to the previously unburned (and undefended) vertices $\sigma_{i+1}\subseteq\bigcup_{j=1}^i\rho_j$ in the graph $G[V(G)\setminus \bigcup_{j=1}^{i-1} \sigma_j]$. Then, defend the vertices in $\sigma_{i+1}$ at time $t=i$. Since $\rho$ is a valid strategy for \CFire, $\sigma$ is a valid strategy for \CFRes and saves precisely the same set of vertices.

Let $\sigma=\{\sigma_1,\dots, \sigma_\ell\}$ be a strategy for an arbitrary instance of \CFRes and consider an instance of \CFire on the same rooted graph, budget and integer $k$. Construct a strategy $\rho$ as an ordered grouping $\rho=((\rho_1^1,\dots,\rho_1^b), \dots, (\rho_\ell^1, \dots, \rho_\ell^b))$ of the vertices in $\bigcup \sigma$ such that, for integers $i, j$ such that $i<j$, $v\in\sigma_i$ and $w\in\sigma_j$ implies that $v$ comes in a group before the group of $w$ in the ordering. Clearly, any such ordering is a valid strategy for \CFire and saves precisely the same number of vertices.
\end{proof}


-----
 
**Consider:**


**Source:** 


**Reference:** 
