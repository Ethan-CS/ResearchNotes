Tags :
Zettel :  20231017-1452
Status : #triage 

-----

# Integer Program for Firefighter

**Previous note:** [[202310131636 Firefighting on Interval Graphs]]

-----

### Questions & thoughts:

The following IP determines $MVS(G,F;d)$ for any $f$-rooted graph $(G,F)$. Here, $T$ is an upper bound on the number of time units needed to contain the fire, and for $0\leq t\leq T$ and $x\in V$, the boolean variables $b_{x,t}$ and $d_{x,t}$ are defined by
$$
\begin{align}
b_{x, t}&=\begin{cases}
1 \hspace{10pt} x \textrm{ burned before or at time } t\\
0 \hspace{10pt} \textrm{otherwise}
\end{cases}
\\
d_{x, t}&= \begin{cases}
0 \hspace{10pt} \textrm{otherwise}
\end{cases}
\end{align}
$$


-----
 
**Consider:**


**Source:** 


**Reference:** 
