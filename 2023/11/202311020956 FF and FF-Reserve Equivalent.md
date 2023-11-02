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

**Lemma 2:**[^1] The Firefighter and Firefighter-with-Reserve problems are equivalent.

**Proof.** Consider a strategy $v_1, \dots, v_k$ for FF and consider FF-Res. At time $t$, if fire reaches vertices $F_t\subseteq \{v_1, \dots, v_k\}$ at time $t+1$ in $G-\bigcup_{i=1}^$


-----
 
**Consider:**


**Source:** 
[1]: Fedor V. Fomin, Pinar Heggernes and Erik Jan van Leeuwen, _The Firefighter problem on graph classes,_ **Theoretical Computer Science** 613 (2016), pp. 38-50, [DOI](https://doi.org/10.1016/j.tcs.2015.11.024)

**Reference:** 
