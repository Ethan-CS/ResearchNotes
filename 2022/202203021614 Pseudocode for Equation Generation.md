Tags :
Zettel :  20220302-1615
Status : #triage 

-----

# Pseudocode for Equation Generation

**Previous note:** [202202211752 Combinatorial Subgraph Searching](202202211752%20Combinatorial%20Subgraph%20Searching.md)

-----

### Questions & thoughts:

Already produced pseudocode (and Java code) for tuple generation, for completeness I would like to have pseudocode for the remaining logic generating equations for tuples. May change complexity!

Get equations:
```
get_equation(tuple):
  # Uses chain rule to differentiate the tuple:
  # d<xyz>/dt = (dx/dt)yz + x(dy/dt)z + xy(dz/dt)
  for each vertex v in tuple:
    # Label v as the current vertex to be differentiated,
	# others will be added back in later
	equation <- empty equation # will store diff eqn for tuple
	get_entry_terms(equation, v, tuple) # Any states that lead to entering state represented by tuple
	get_exit_terms(v, tuple) # Similar for states leading out of tuple

```

Get exit terms:
```
get_exit_terms(equation, v, tuple):
  other_terms <- tuple 
  s <- state that v inhabits
  exiting_states <- states that can transition from s
  for each state t in exiting_states:
  	rate <- transition rate from s to t
	if we need neighbour(s) to enter s:
	  for each vertex w adjacent to v:
	    if w not in other_terms:
		  add w to other_terms
		equation <- add_exit_tuple(equation, other_terms, rate)
		remove w from other_terms
   remove v from other_terms
  else if transition out of s occurs without a neighbour:
    equation <- add_exit_tuple(equation, other_terms, rate)
  return equation

add_exit_tuple(equation, other_terms, rate):
  if other_terms constitutes a tuple in list of required tuples:
    equation -= (rate * Pr(other_terms)) # Pr(X) <- probability of X
  return equation
```

Get entry terms:
```
get_entry_terms(equation, v, tuple):
  other_terms <- tuple without v
  s <- state that v inhabits
  inducing_states <- states that can transition to s
  for each state t in inducing_states:
    rate <- transition rate from t to s
    v_before <- vertex v in state t # v in state it could have been in before s
	add v_before to other_terms
	if we need neighbour(s) to enter s:
	  for each vertex w adjacent to v:
	    if w not in other_terms:
		  add w to other_terms
	    equation <- add_entry_tuple(equation, other_terms, rate)
		remove w from other_terms
    else if transition into s occurs without a neighbour:
      equation <- add_exit_tuple(equation, other_terms, rate)
	remove v_before from other_states
  return equation
  
add_entry_tuple(equation, other_terms, rate):
  if other_terms constitutes a tuple in list of required tuples:
    equation += (rate * Pr(other_terms)) # Pr(X) <- probability of X
  return equation
```

-----

