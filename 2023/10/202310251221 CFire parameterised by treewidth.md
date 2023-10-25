Tags : #msol #logic #parameterised 
Zettel :  20231025-1221
Status : #triage 

-----

# CFIre parameterised by treewidth

**Previous note:** [[202310241018 FF on P_k-free graphs]]

-----

### Questions & thoughts:

Conjecture: CFire is FPT when parameterised by treewidth of input graph (and $k$, number of vertices saved).

Let $(G, r, k, b, c:V\rightarrow\mathbb{Z})$ be an instance of CFire such that the treewidth of $G$ is $w$. Let $p_i^j$ represent the $j$-th vertex defended at timestep $i$ and let $B_i$ be the vertices burning at timestep $i$. Let $A:V(G)\times V(G)\rightarrow\{\texttt{true}, \texttt{false}\}$ be a function that returns true if two vertices are adjacent and false otherwise in the graph $G$. Consider the following MSO formula:
$$
\begin{align}
\textrm{NextToBurn}&(B_{i-1}, B, p_1^1,\dots, p_1^{b_1},\dots,p_i^1, \dots, p_i^{b_i})\\
&:=\forall v\in V(G)\left(\left(v\in B_{i-1}\vee\exists u\in V(G) \left(\right)\right)\right)
\end{align}
$$



-----
 
**Consider:**


**Source:** 


**Reference:** 
