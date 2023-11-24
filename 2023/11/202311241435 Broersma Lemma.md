Tags :
Zettel :  20231124-1436
Status : #triage 

-----

# Broersma Lemma

**Previous note:** [[202311231101 Nice way to paper-ise work on FF?]]

-----

### Questions & thoughts:

From paper:[^1]

A proper subset $S \subset V$ is a separator of $G$ if $G − S=G[V(G)\subseteq S]$ is disconnected.

**Definition 8**. A vertex set $S\subset V$ is an $(a,b)$-separator of $G$ if the removal of $S$ separates $a$ and $b$ in distinct connected components of $G − S$. If no proper subset of an $(a,b)$-separator $S$ is an $(a,b)$-separator, then $S$ is a minimal $(a,b)$-separator. A vertex set $S \subset V$ is a minimal separator of $G$ if there exist nonadjacent vertices $a$ and $b$ in $G$ such that $S$ is a minimal $(a,b)$-separator of $G$.

**Definition 18.** A set $\mathfrak{S}$ of minimal separators of $G$ is a *blocking set* if the elements of $\mathfrak{S}$ are incomparable with respect to set inclusion and for all $S \in \mathfrak{S}$ the vertex set $(\bigcup \mathfrak{S})\setminus S$ is contained in one connected component of $G − S$.

Note that in particular any singleton consisting of a minimal separator of $G$ is a blocking set.

**Definition 19**. Let $\mathfrak{S}$ be a blocking set of $G$ with $|\mathfrak{S}| \geq 2$.Then, a vertex $v \in V\setminus \bigcup \mathfrak{S}$ is said to be in the *interior* of $\mathfrak{S}$ if, for every $S \in \mathfrak{S}$, the vertex $v$ and the vertex set $\bigcup\mathfrak{S}\setminus S$ are contained in one connected component of $G − S$.

Denote the maximum cardinality of an asteroidal set of a graph $G$ by $\textrm{an}(G)$.

**Lemma 20**. For every blocking set $\mathfrak{S}$ of $G$, $|\mathfrak{S}| \leq \textrm{an}(G)$.

-----
 
**Consider:**


**Reference:**

[1]: Broersma, Kloks, Kratsch _et al._ A Generalization of AT-Free Graphs and a Generic Algorithm for Solving Triangulation Problems . _Algorithmica_ **32**, 594–610 (2002). https://doi.org/10.1007/s00453-001-0091-x