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
 - If the graph contains at least one cut-vertices (and user has specified closures should be considered), set `closures` to `TRUE`, otherwise set `closures` to `FALSE`.
 - Initialise:
	 - List `equations<-single_vertex_equations(...)` with equations for single-vertex terms:
	 - For each vertex $v$ in $G$:
		 - For each non-terminal state $\sigma$ in $M$:
			 - Add an equation for $\langle \sigma_v\rangle$ to the list of equations using the master equation
	 - Set of terms added to RHS of equations
 - Length $l=1$
 - while $l\leq V(G)$:
 - For any term $t$ in set of terms added to equations:
	 - If $t$ does not yet appear on the LHS of an equation in the list of equations, add an equation for it (and update the set of RHS terms):
	 - Chain rule on $t$, e.g. $\langle S_1 I_2 \rangle\rightarrow\dot{\langle S_1 \rangle}\langle I_2 \rangle + \langle S_1 \rangle \dot{\langle I_2 \rangle}$, and substitute derivative terms using existing equation
	 - 
 - Return list of equations.

The first equations generated are those for single-vertex terms: a complete representation of the system dynamics includes equations for each vertex in each non-terminal model state. The equations for each term are determined using the master equation - this involves considering model projections that could lead into and out of the model projection represented by each term. Then, we recursively add to the system equations for moments of terms that have been added in previous equations (for example, if an equation for $\langle S_1 \rangle$ includes the term $\langle S_1 I_2\rangle$, we now need to add an equation for the latter) until we have written an equation for each term in the right hand side of any other equations. Each equation for terms of length two or more is added using the chain rule, as outlined in and subject to caveats from \cite{sharkey_2013}.


-----
 
**Consider:**


**Source:** 


**Reference:** 
