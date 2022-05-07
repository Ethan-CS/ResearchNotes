Tags :
Zettel :  20220504-1439
Status : #triage 

-----

# Path Decomposition of a Graph

**Previous note:** [[]]

-----

### Questions & thoughts:

Jess and I discussed path/tree decomposition as a useful tool in equation generation procedure.


**Def: Path Decomposition.** A _decomposition_ of a graph $G$ is a collection $\psi$ of edge-disjoint subgraphs $H_1, H_2, \dots, H_r$ of $G$ such that every edge of $G$ belongs to exactly one $H_i.$ 
 - If each $H_i$ is a path or a cycle in $G$, then $\psi$ is called a _path decomposition_ of $G$. 
 - If each $H_i$ is a path in $G$, then $\psi$ is called an _acyclic path decomposition_ of $G$.

How can this help us in equation generation?

One idea:

Take a graph $G$ -> Get the graph decomposition $\psi$ -> Generate equations for paths

This would mean we can make use of the fact that number of equations on paths/cycles is quadratic in the number of vertices on the path, so would scale better in some cases than just generating on $G$. However, some questions need answering:

- What is the complexity of the second step (finding the path decomposition)?
- How do we link everything together? Can we use the result from the Kiss paper?
- Is this the "natural extension" of the main result in the Kiss paper?


-----
 
**Consider:**


**Source:** 


**Reference:** 
