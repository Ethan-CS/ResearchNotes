Tags :
Zettel :  20240918-1415
Status : #triage 

-----

# Another problem

**Previous note:** [[202409161823 CFire on interval graphs]]

-----

### Questions & thoughts:

I'm considering **Cost Function Fire** on **chordal graphs.** To think about chordal graphs, I'm using their **clique tree representations.**

I think there is a DP approach somewhere in all this (Cost Fn Fire on chordal graphs) that leverages the clique tree representation, but where to start? I get stuck at the recursion!

Similar problem:
Fire with weighted edges: Fire on a weighted, directed graph in which the edge weights indicate the cost of removing that edge.

Similarity of Weighted Edge Firefighter to Cost Fire on Trees: edge weights can indicate sum of costs of vertices the to-clique that are adjacent to something in the from-clique, i.e. the vertices that need to be defended for these cliques to no longer be connected. Severing either the from-to direction or the to-from direction knocks out the connection, so the other edge should disappear and we use the cheapest possible. Hence, maybe we can use a directed graph with weights corresponding to the cheapest such set in each case of pairwise connected cliques?

This has probably been studied. Can we prove that this is equivalent to solving on clique tree? And does this give us immediate results?


-----
