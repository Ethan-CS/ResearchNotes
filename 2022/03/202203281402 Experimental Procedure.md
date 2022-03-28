Tags :
Zettel :  20220328-1402
Status : #triage 

-----

# Experimental Procedure

**Previous note:** [202203162248 Connectedness in ER Graphs](202203162248%20Connectedness%20in%20ER%20Graphs.md)

-----

### Questions & thoughts:

__PROCEDURES:__

1. How feasible is exact equation generation on a certain random graph class?
	1. Input parameters: number of graphs, any graph input requirements (e.g. number of vertices, probability/number of edges)
	2. Generate specified number of graphs. For each graph, determine required number of equations and print in some analysable format (good start might be CSV).
	3. Plot the results and see if there is a clear cut-off.
	4. Compare any potential cut-offs with any known results about connectedness/density/etc. in particular graph class.
2. When is exact equation generation faster than simulation for a certain class of random graph?
	1. Input parameters: number of graphs to test, acceptable range from exact solution simulation average must land inside, model to use.
	2. For each graph, generate equations and solve.
	3. Run simulations of model on generated graph until average result comes within the specified range of the actual solution found in the previous step - terminate yielding time taken to obtain result.



-----
 
**Consider:**


**Source:** 


**Reference:** 
