
Tags :
Zettel :  20230621-1411
Status : #triage 

-----

# Claim about WDF Hardness

**Previous note:** [202306211211 WDF Restrictions](202306211211%20WDF%20Restrictions.md)

-----

### Questions & thoughts:

**Claim:** WDF is polynomial time solvable on a rooted graph $(G, r)$ with maximum degree $\Delta$ and budget $b$ if the following are all true:
1. $\texttt{deg}(r)\leq\Delta-1$
2. $\forall t\in\{1, 2, \do\}$,  $\forall v\in V\setminus\displaystyle\bigcup_{i=0}^tf_i\cup d_i$, if  $\exists w\in\displaystyle\bigcup_{i=0}^tf_i$ such that $\textrm{dist}(v, w)=1$ then $c(v, t)\leq c(w, t)$
3. At every timestep $t$, for any two vertices $v_1$ and $v_2$ both adjacent to fire, $c(v_1, t)=v(v_2, t)$
4. At every timestep $t$, $b$ is such that at least $\Delta-2$ vertices can be defended 

Start with (1): what happens if the fire can start anywhere?


-----
 
**Consider:**


**Source:** 


**Reference:** 
