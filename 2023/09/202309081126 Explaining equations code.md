Tags :
Zettel :  20230908-1126
Status : #triage 

-----

# Explaining equations code

**Previous note:** [[202309061645 State-of-Play of Revisions]]

-----

### Questions & thoughts:

`generate_equations`: generates the required equations for a given graph $G$ and model $M$.
 - Initialise a boolean variable `closures`
 - If the graph contains at least one cut-vertices (and user has specified closures should be considered), `closures <- TRUE` else `FALSE`.
 - Initialise:
	 - List `equations<-single_vertex_equations(...)` with equations for single-vertex terms:
	 - For each vertex $v$ in $G$:
		 - For each non-terminal state $S$ in $M$:
			 - Add an equation for $\langle S_v\rangle$ to the list of equations using the master equation
		 - End
	 - End
	 - Set of terms added to RHS of equations
 - Length $l=1$
 - while $l\leq V(G)$:
 - For any term $t$ in set of terms added to equations:
	 - If $t$ does not yet appear on the LHS of an equation in the list of equations, add an equation for it (and update the set of RHS terms):
	 - Chain rule on $t$, e.g. $\langle S_1 I_2 \rangle\rightarrow\dot{\langle S_1 \rangle}\langle I_2 \rangle + \langle S_1 \rangle \dot{\langle I_2 \rangle}$, and replace derivative terms with existing equation
	 - 
 - Return list of equations.


-----
 
**Consider:**


**Source:** 


**Reference:** 
