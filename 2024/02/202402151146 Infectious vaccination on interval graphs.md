Tags :
Zettel :  20240215-1146
Status : #triage 

-----

# Infectious vaccination on interval graphs

**Previous note:** [[202402081136 Open problems in spreading Firefighter problem]]

-----

### Questions & thoughts:

**Claim.** Let $(G, r)$ be a rooted interval graph such that $r$ corresponds to the leftmost interval in the interval representation of $G$. The infectious defence firefighter problem can be ended after a single time-step.

**Proof.** At time $t=0$, fire breaks out at $r$, the interval with leftmost left endpoint in the interval representation of $G$. In this interval representation, consider the set of intervals $I$ that intersect intervals that neighbour $r$ but do not intersect the interval $r$. At time $t=1$, defend the vertex that corresponds to an interval in $I$ with rightmost right endpoint of intervals in $I$. Then, fire spreads to the neighbours of $r$. Now, defence spreads to vertices corresponding to the other intervals in $I$. Now, the neighbours of $r$ are now burning but their neighbours are defended, so the fire is contained and we do not proceed to a second time-step.

The argument for the same result where $r$ corresponds to the rightmost interval in the interval representation of $G$ is symmetric. 



-----
 
**Consider:** extend this argument for $r$ not being left- or right-most.