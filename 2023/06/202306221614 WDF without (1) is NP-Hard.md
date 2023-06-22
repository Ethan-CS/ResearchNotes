Tags : #NP-Hard #Firefighter 
Zettel :  20230622-1614
Status : #triage 

-----

# WDF without (1) is NP-Hard

**Previous note:** [202306221137 Erik Demaine Complexity Lecture](202306221137%20Erik%20Demaine%20Complexity%20Lecture.md)

-----

### Questions & thoughts:

**Result**: Firefighter problem is NP-Complete for rooted graphs $(G, r)$ such that $\Delta(G)=3$ and $\textrm{deg}(r)=3$.[^1] 

Either a **Claim** or a **corollary** of the above result: Firefighter is NP-Complete for rooted graphs $(G, r)$ with budget $b$ such that $\Delta(G)=\textrm{deg}(r)=b+2$.

Call the above restriction of Firefighter FF'. Define a new problem WDF' that is WDF on the same restricted class of graph.

**Result:** FF' $\leq_\textrm{P}$ WDF', i.e. WDF' is NP-Hard.

Proof. Consider any instance of FF' on a rooted graph $(G, r)$ and a budget $b\in\mathbb{Z_{>0}}$ such that $\Delta(G)=b+2$ and $\textrm{deg}(r)=b+2$. Consider an instance of WDF' on a rooted graph $(G, r)$ such that $\Delta(G)=bd+2$, where $d$ is the number of vertices that can be defended adjac with vertex set $V$, budget $b\in\mathbb{Z_{>0}}$, set of time-steps $T$  and cost function $\forall v\in V, \forall t \in T, c(v, t)=1$ i.e., precisely $b$ vertices can be defended at each time-step 

-----
 
**Consider:**


**Source:** 


**Reference:** 


[^1]: S Finbow, A King, G MacGillivray, R Rizzi, The firefighter problem for graphs of maximum degree three, Discrete Mathematics 307 (2007), 2094-2105