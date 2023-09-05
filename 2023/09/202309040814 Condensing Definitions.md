Tags :
Zettel :  20230904-0814
Status : #triage 

-----

# Condensing Definitions

**Previous note:** [202308291341 Addressing Manuscript Reviews](202308291341%20Addressing%20Manuscript%20Reviews.md)

-----

### Questions & thoughts:

For completeness and due to the interdisciplinary nature of our work, we note some standard graph theory definitions that are used throughout. A *digraph* (or *directed graph*) $G=(V,E)$ is a pair composed of a finite set $V$ called the *vertices* and an irreflexive binary relation on $V$ called an *adjacency relation* represented as a set $E$ of ordered pairs of vertices $\{(v_i, v_j)~|~v_i, v_j \in V\} \subseteq V\times V$ called the *edges*. An *undirected graph* $G=(V,E)$ is a digraph in which the adjacency relation is symmetric i.e., $E=E^{-1}.$ Unless otherwise stated, in this paper we use undirected graphs and refer to them simply as "graphs." While we define the following notions on graphs, we could analogously define them on digraphs. 

A *weighted graph* $(G, w)$ is pair composed of a graph $G=(V, E)$ and a weight function $w:E\rightarrow\mathbb{R}$, where $w(e)$ refers to the *weight* of $e\in E.$ For a graph $G=(V, E),$ a *subgraph* $H=(V_H, E_H)$, denoted $H\subseteq G$, is a graph on a vertex-set $V_H\subseteq V$ and edge-set $E_H=\{\{v_i, v_j\}~|~v_i, v_j\in V_H\}\subseteq E.$ An *induced subgraph* is a graph on a vertex-set $V_H\subseteq V$ and an edge-set consisting of all edges $\{v_i, v_j\} \in E$ for $v_i, v_j\in V_H$. The subgraph of $G$ induced by $V_H$ is denoted $G[V_H].$ A *component* of a graph $G$ is an induced subgraph $G[V_H]\subseteq G$ such that the graphs $G[V_H]$ and $G\setminus G[V_H]$ are disconnected i.e., for any vertices $v_i$ and $v_j$ in $G$ and $G[V_H]$ respectively, there is no sequence of pairwise connected vertices $(v_i, v_{i+1}, \dots, v_{j})$. A component $C\subseteq G$ is a maximal connected induced subgraph of $G.$


-----
 
**Consider:**


**Source:** 


**Reference:** 
