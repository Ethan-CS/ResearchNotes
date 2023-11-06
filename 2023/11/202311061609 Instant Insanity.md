Tags :
Zettel :  20231106-1609
Status : #triage 

-----

# Instant Insanity (Favourite Reduction Session)

**Previous note:** [[202311061145 CFF and CFF-Res equivalent]]

-----

### Questions & thoughts:

**Expressing Instant Insanity as a Graph Problem**
 1. Draw four vertices and label them B, G, R, Y (blue, green, red, yellow)
 2. Number the cubes from 1 to 4 and for each of the three pairs of opposite faces on each cube, draw an edge between the two vertices of the corresponding colours and label that edge by that cube number (a total of 12 edges).
 3. Look for a _Hamilton cycle_ (a cycle that passes through each vertex precisely once) with a different label on each edge
 4. Find a second Hamilton cycle with a different label on each edge, that does not uses any of the edges in the first cycle; this cycle is shown with the hashed edges in the figure below.
 5. Traverse the thick edge cycle to set the top edges.
 6. Set the front/back edges with the hashed cycle by rotating each cube (without changing the top and bottom).

Efficient algorithms are not known for finding Hamilton cycles (let alone two disjoint ones). However, this is a small graph, and it provides an organized way to search for these two cycles rather than playing with the cubes and trying to remember what has been tried.****



-----
 
**Consider:**


**Source:** 


**Reference:** 
