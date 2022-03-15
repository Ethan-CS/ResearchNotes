Tags :   #Code #Counting #ODE 
Zettel :  20220221-1752
Status : #triage 

-----

# Implementing a Combinatorial Subgraph Searching Algorithm

-----

### Questions & thoughts:

First attempt at some pseudocode for this:

```
# Combinatorial subgraph search function
# input:  G - the graph to find all subgraphs of
# output: all sub-graphs of G
comb_search(G):
	all_states # 2D array - all states stored by num vertices in state
	for vertex v in G:
		expand <- [v]
		while expand is not empty:
			x <- first elem of expand
			remove x from expand
			children <- generator(x) # Get all children of x
			expand <- list(expand, children) # Add children to expand
			add x to all_states[size of x]
	return all_states

# Generator function
# input:  state      - the current state to find children of
#		  all_states - all states found so far
# output: all successor states to the inputted state 
generator(state, all_states):
	children
	for vertex v in state:
		for vertex w in neighbours of v:
			child <- list(state, w) # Child is state with w appended
			if (child not in all_states[size of child]): # No duplicates
				add child to children
	return children	
				
```

Added to HackMD for feedback [here](https://hackmd.io/@2dkYNbTEQqSgWui5OwM4MA/rywF5Dbgq)

-----
 
**Consider:**


**Source:** 


**Reference:** 
