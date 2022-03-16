Tags :
Zettel :  20220315-1751
Status : #triage 

-----

# Equation Generation Experiments

**Previous note:** [202203021614 Pseudocode for Equation Generation](202203021614%20Pseudocode%20for%20Equation%20Generation.md)

-----

### Questions & thoughts:

__Research question: for what values of $p$ can we feasibly generate equations for Erdos-Renyi graphs on $n$ vertices?__

Start: it's likely a somewhat imprecise upper bound is $p<<\frac{\log{n}}{n}$ as such values of $p$ means we expect many isolated vertices (i.e. very unlikely the graph is connected)[^1].

Input:
- `iter` - number of iterations
- `n` - number of vertices
- `p_min` - minimum (starting) probability, `p_incr` - amount to increment p each time; `p_max` - maximum probability

Process:
- For each value of `p` between `p_min`  and `p_max`, generate `iter`-many ER graphs on `n` vertices and probability `p`.
- For each of these graphs, use the previously written procedures to determine the required number of equations.
- Record the numbers of equations for each of these graphs and plot the results using box plots to compare the averages and ranges of results.
- Use the recorded results as evidence towards an answer to the research question


-----
 
**Consider:**

How can we use a similar process to address analogous questions for other random graph classes? 

Which other graph classes could/should we run these experiments on?

Statistical significance: need a formal way of determining answers to research questions, involving averages.

Next: aim to identify cut-off (experimentally) with averaging simulated behaviour. Need:
 - Code for simulations (have some old code, good start at least)
 - Code for generating and solving equations (generating fine but solving no longer works, needs to be fixed)
 - Code that compares these results - when does it take longer for MC average to reach a specified distance from exact value calculated from equation generation and solving than time taken to generate equations and solve? And vice versa.


**Source:** 


**Reference:** 
[1]:  Connected components in Erdos-Renyi random graphs, Karen Gunderson, Lecture Notes, 2013