Tags : #parameterised #proof #firefighter
Zettel :  20231019-1237
Status : #triage 

-----

# Proof: Defence strategy for Firefighter in poly time

**Previous note:** [[202310171452 IP for Firefighter]]

-----

### Questions & thoughts:

Original lemma (1):[^1] given a rooted graph $(G, r)$ on $n$ vertices and $m$ edges, we can verify whether the ordered list of vertices in $G$, $S=\{v_1,\dots,v_k\}$ is a valid strategy for Firefighter on $(G, r)$ and count the number of vertices the strategy saves in $O(n+m)$ time.

Original proof:
 - For each integer $i=1, \dots, k$, define $S_i=\{v_1, \dots, v_i\}$.
 - Play Firefighter: fire breaks out at $r$
 - Use an adapted BFS to check that for each $i=1,\dots,k$, $v_i$ is neither burned nor defended at time $t=i$ i.e., $v_i\notin R_i(r)$ where $R_1(r)=\{r\}$ and $R_i(r)=N_{G\setminus S_{i-1}}[R_i-1(r)]$.
 - By playing Firefighter, we can check the game ends at time step $k$.
 - If the above has been successful, we can compute the number of vertices saved by $S$ as $n$ minus number of vertices reachable from $r$ in $G\setminus S$ using a BFS from $r$ in $G\setminus S$

Pseudocode:
```
Algorithm: verifying strategy and computing saved vertices for a Firefighter game

Input:
- Graph G
- Integer k
- Root vertex r
- Strategy S

Output:
- Number of saved vertices

1. Initialise a list R=[R_1=[r]]
2. Initialise a counter saved_vertices to keep track of saved vertices.
3. Play the Firefighter game by starting with a fire breaking out at vertex r.
4. Use an adapted BFS (Breadth-First Search) to update the sets R_i based on the current state of the graph
d. Check whether the i-th vertex in S is neither burned nor defended at time t=i.
e. If v_i is safe, increment the saved_vertices counter.
1. Check if the game ends at time step k by comparing saved_vertices to k.
2. If the game ends (i.e., saved_vertices equals k), compute the number of vertices saved by set S as follows:
   a. Find the number of vertices reachable from the starting vertex r in the subgraph G\S (complement of S) using a BFS.
   b. Subtract the number of reachable vertices from the total number of vertices in G to determine the saved vertices.
6. Return the computed number of saved vertices.

```



-----
 
**Consider:**


**Source:** 

[1]: Lemma 1 in [this](https://doi.org/10.1016/j.tcs.2015.11.024) paper


**Reference:** 
