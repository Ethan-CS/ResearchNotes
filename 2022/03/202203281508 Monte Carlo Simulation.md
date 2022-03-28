Tags :
Zettel :  20220328-1508
Status : #triage 

-----

# Monte Carlo Simulation

**Previous note:** [202203281402 Experimental Procedure](202203281402%20Experimental%20Procedure.md)

-----

### Questions & thoughts:

Process of Monte Carlo simulation of an $SIR$ epidemic on a graph.

Input:
- Graph
- Model params
	- Rate of infection
	- Rate of recovery
- Source vertices (can be randomly selected)

For each set of source vertices, run usual SIR model:
- $n$ initially infected nodes, with probability $p$ and recovery time $r$ selected from a given population distribution.
- At each time-step, each infected vertex can transmit to any neighbours with probability $p,$ which may decay in time as individuals realise they are infected and begin to be more cautious not to transmit.
- Infected vertices are removed after $r$ time-steps, at which point the individual gains either post-infection immunity or is deceased. 



-----
 
**Consider:** Easiest/simplest thing might be to create a fresh project. Agency project from last year may have necessary simulation code, although this is probably in need of debugging. Alternatively, could write code in a new package in current ODE Java project, although could make the whole project a little unnecessarily bloated.


**Source:** [Infection Modeling — Part 1, Mark Ditsworth](https://towardsdatascience.com/infection-modeling-part-1-87e74645568a)
