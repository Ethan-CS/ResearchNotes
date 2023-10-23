Tags : #parameterised #proof #firefighter
Zettel :  20231019-1237
Status : #triage 

-----

# Proof: Defence strategy for Firefighter in poly time

**Previous note:** [[202310171452 IP for Firefighter]]

-----

### Questions & thoughts:

Original lemma:[^1] given a rooted graph $(G, r)$ on $n$ vertices and $m$ edges, we can verify whether the ordered list of vertices in $G$, $S=\{v_1,\dots,v_k\}$ is a valid strategy for Firefighter on $(G, r)$ and count the number of vertices the strategy saves in $O(n+m)$ time.

Original proof:
 - For each integer $i=1, \dots, k$, define $S_i=\{v_1, \dots, v_i\}$.
 - Play Firefighter: fire breaks out at $r$
 - Use an adapted BFS to check that for each $i=1,\dots,k$, $v_i$ is neither burned nor defended at time $t=i$ i.e., $v_i\notin R_i(r)$ where $R_1(r)=\{r\}$ and $R_i(r)=N_{G\setminus S_{i-1}}[R_i-1(r)]$.
 - By playing Firefighter, we can check the game ends at time step $k$.
 - If the above has been successful, we can compute the number of vertices saved by $S$ as $n$ minus number of vertices reachable from $r$ in $G\setminus S$ using a BFS from $r$ in $G\setminus S$





-----
 
**Consider:**


**Source:** 

[1]: Lemma 1 in [this](https://doi.org/10.1016/j.tcs.2015.11.024) paper


**Reference:** 
