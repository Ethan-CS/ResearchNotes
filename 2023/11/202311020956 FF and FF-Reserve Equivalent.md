Tags : #Firefighter #Firefighter-reserve 
Zettel :  20231102-0956
Status : #triage 

-----

# Firefighter and Firefighter-with-Reserve are equivalent

**Previous note:** [[202310311548 FF on Interval Graphs]]

-----

### Questions & thoughts:

### Firefighter-with-reserve game definition

As given in:[^1] in the Firefighter-with-Reserve game on a rooted graph $(G, r)$, a fire starts at $r$ at time $t=0$ and the firefighters have a reserve of one. At each subsequent timestep $t\geq 1$, first the firefighters can deploy any number of defences on the vertices of $G$ up to the current value of the reserve, with the reserve decreasing accordingly. Then, the fire spreads to every undefended and unburned neighbour adjacent to a burning vertex. Then, a firefighter is added to the reserve and a new timestep starts. The game ends when the fire can no longer spread to any adjacent vertices. 

### Equivalence to Firefighter

***(Earlier) Lemma 2:** The Firefighter and the Firefighter Reserve Deployment problem are equivalent.*  

**Proof.** 
 1. Consider a strategy $v_1,\dots,v_k$ for the Firefighting game.
 2. At time step t, if the fire reaches vertices $F_t \subseteq \{v_1,\dots,v_k\}$ at time step $t +1$ in $G\setminus\bigcup_{i=1}^{t−1}F_i$, deploy the firefighters in $F_t$ at time $t$. 
**C1:** Because $v_1,\dots,v_k$ is a valid strategy, this must also be a valid strategy that saves exactly the same set of vertices. 
3. Consider a strategy $F_1,\dots,F_k$ for the Firefighting-with-Reserve game. 
4. Consider any ordering $v_1,\dots,v_k^\prime$ of the vertices in $F_1,...,F_k$ such that $v_a \in F_i, v_b \in F_j$ for $i< j$ implies $a<b$. 
**C2:** Because $F_1,\dots,F_k$ is a valid strategy, this ordering is also a valid strategy. 
**C3:** this new strategy saves exactly the same set of vertices.  
**C:** Firefighter and Firefighter-Reserve-Deployment are equivalent problems. $\blacksquare$

Consider the two transformations in the above proof. If we apply the second transformation on a strategy for the Firefighting-with-Reserve game, and then the first, we obtain a strategy for the Firefighting-with-Reserve game with the following property.

***(Earlier) Corollary 3 (of Lemma 2):**[^1] Let $(G, s)$ be an instance of Firefighter Reserve Deployment. There exists an optimal strategy for the Firefighting-with- Reserve game on $(G , s)$ that only protects vertices that neighbour a vertex that is on fire.


-----
 
**Consider:**


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)

**Reference:** 
