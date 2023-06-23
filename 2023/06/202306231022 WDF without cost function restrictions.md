Tags : #WDF #Firefighter #complexity 
Zettel :  20230623-1022
Status : #triage 

-----

# WDF without cost function restrictions

**Previous note:** [202306221614 WDF without (1) is NP-Hard](202306221614%20WDF%20without%20(1)%20is%20NP-Hard.md)

**See list of conditions:** [202306211211 WDF Restrictions](202306211211%20WDF%20Restrictions.md), [202306211411 Claim about WDF Hardness](202306211411%20Claim%20about%20WDF%20Hardness.md)

-----

### Questions & thoughts:

C Duffy in his Masters thesis https://dspace.library.uvic.ca/handle/1828/3550 proved that WFIRE is NP-Complete even when restricted to binary trees where $\textrm{deg}(r)=2$.

Corollary (according to C Wagner's MSc thesis A New Survey on the Firefighter Problem, although I need to convince myself it is a legitimate corollary): $b$-WFIRE is NP-Complete on trees of maximum degree $b+2$ even when the degree of the root is $b+1$.

We prove that WDF without cost function restrictions (2 and 3) is NP-Complete even on trees (graphs?) of maximum degree $b+2$ where the root is of degree $b+1$.

**WFIRE**
 - Instance: rooted graph $(G, r)$, integer $k$, weight function $w:V(G)\rightarrow\mathbb{Z}$.
 - Question: is $MVS_w(G, r)\geq k$?

Instance of WDF: rooted graph $(G, r)$ such that $\Delta(G)=3$ and $\textrm{deg}(r)=2$, an integer $k\geq1$, a weight function $c:V(G)\times \{1, 2, \dots, |V(G)|\}\rightarrow\mathbb{Z}\subset\mathbb{R}$ that is uniformly integer valued  across  all vertices, i.e. 
$$\forall i,j\in \{1,\,2, \dots, |V(G)|\}, \forall v\in V(G), c(v, i)=c(v, j).$$





-----
 
**Consider:**


**Source:** 


**Reference:** 

