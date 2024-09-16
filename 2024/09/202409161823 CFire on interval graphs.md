Tags :
Zettel :  20240916-1823
Status : #triage 

-----

# CFire on interval graphs

**Previous note:** [[202408161357 Feedback by Section]]

-----

### Questions & thoughts:


**Theorem.** CFire can be solved in time $O(?)$ on interval graphs on $n$ vertices.

(I'm not even sure this is possible, but I think it is!)

"Proof."
 - Let $G=(V, E)$ be an interval graph with $n$ vertices and $b$ be per-turn budget
 - Obtain the interval representation $I$ of $G$ (in $O(n)$-time) and sort them with respect to their right endpoints (in O(n ln(n))-time using e.g. comparison sort).
 - Dynamic programming:
	 - Create a table $DP$ in which each $DP[i][t]$ for interval $i$ at time $t$ representing max number of vertices that can be saved.
	 - Fill bottom-up, from rightmost right endpoint to leftmost.
	 - Recurrence: $$DP[i][\sigma][t]=\begin{cases}DP[i-1][\sigma][t] &\textrm{don't defend }i\\\max(DP[i-1][\sigma^\prime][t], DP[j][t-c_i]+(i-j))&\textrm{defend } i\end{cases}$$ where $j$ is the rightmost interval to left of leftmost interval of $i$
	 - Base case is set as $DP[i][0]=0$ and $DP[0][t]=0$ for all $i$ and $t$ respectively 
	 - We look at $DP[n][T]$ to find the max number of vertices we can save by considering all $n$ intervals and entire budget $b$
 - By sorting intervals, we process intervals in order fire would spread
 - At each time $i$, do or don't defend each interval and see what happens.



-----
 
**Consider:**


**Source:** 


**Reference:** 
