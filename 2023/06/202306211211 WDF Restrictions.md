Tags : #Firefighter #complexity
Zettel :  20230621-1212
Status : #triage 

-----

# Firefighter Variation Restrictions

-----

### Questions & thoughts:

Under which conditions can we claim WDF is poly time solvable? Seems we need, for max degree $\Delta$:
 - Graph with max degree $\Delta$ rooted at a vertex of degree $\Delta-1$
 - Not more expensive to defend beside fire than elsewhere in graph
 - Uniform cost to defend beside fire? I.e. one vertex with burning neighbour no cheaper/more expensive than another?
 - Budget and cost to defend beside fire such that at least $\Delta-2$ can be defended each time-step

Beginning at bottom, with nothing else specified about the instance, consider which can be removed and problem is NP-Hard (take an instance of e.g. Firefighter-Tree and reduce to instance of WDF where each (set of) condition(s) are removed). Do we end up with a _dichotomy result?_ This is somewhere where if true then hard, if false then easy.


-----
 
**Consider:**
 - Are all these conditions correct for poly time solveable?
 - Change the problem definition in APR and paper to not hardcode peril function to satisfy these conditions - this is part of the _restriction_ not the instance.
 - Look at MIT Lectures from Eric Demaines on hardness/parameterised complexity/etc.