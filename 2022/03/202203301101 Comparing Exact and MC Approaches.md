Tags :
Zettel :  20220330-1101
Status : #triage 

-----

# Comparing Exact and MC Approaches

**Previous note:** [202203281508 Monte Carlo Simulation](202203281508%20Monte%20Carlo%20Simulation.md)

-----

### Questions & thoughts:

I've now written the necessary code for Monte Carlo simulations. How should I now directly compare time taken to generate code from exact and MC approaches?

- Define:
	- Initial conditions
	- Statistical significance - how close can simulated average results be to exact result for us to end simulations?
- Generate equations and solve to obtain exact results
- Input initial conditions to a simulation instance
- Simulate until results average is within defined distance of the exact results
	- Practical note: how long should we wait until calling off simulations without convergence on specified results?

-----
 
**Consider:**
- Fix equation generation code to ensure generated equations are correct and can be solved
- Write a new driver method to follow above process for comparisons, storing the times in some analysable format (e.g. csv is a reasonable start point)
