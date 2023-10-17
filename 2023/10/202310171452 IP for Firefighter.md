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
1 \hspace{10pt} x \textrm{ defended before or at time } t\\
0 \hspace{10pt} \textrm{otherwise}
\end{cases}
\end{align}
$$
**Explanation.** "The first (second) set of constraints assures that a vertex burning (defended) at time t − 1 is still burning (defended) at time t. The third set of constraints assures that every neighbour of a vertex burning at time t−1 is burning or defended at time t. The fourth set of constraints assures that no vertex can be both burning and defended at any time. The fifth set of constraints prevents a vertex with no burning neighbours at time t − 1 from burning at time t. The sixth set of constraints guarantees that at most d firefighters are used per time step. Finally, the next two sets of constraints initialize the variables corresponding to time t = 0."

$$
\displaystyle\textrm{min}\sum_{x\in V}b_{x,T}
$$
subject to:
$$
\begin{align}
\begin{cases}
&b{x,t} \geq b_{x, t-1} & x\in V, 1\leq t \leq T\\
&d{x,t} \geq d_{x, t-1} & x\in V, 1\leq t \leq T\\
&b_{x,t}+d_{x,t}\geq b_{y, t-1} & x\in V,y\in N(X), 1\leq t \leq T\\
&b_{x, t}+d_{x, t}\leq 1 & x\in V, 1\leq t \leq T\\
&\sum_{y\in N(X)}(b_{y, t-1}\geq b_{x, t})&x\in V, 1\leq t \leq T\\
&\sum_{x\in V}(d_{x, t}-d_{x, t-1}\leq d)& 1\leq t \leq T\\
&d_{x,0}=0 &x\in V\\
&b_{x,0}=\begin{align*}\begin{cases}
		     
		 \end{cases}\end{align*}

\end{cases}
\end{align}
$$

-----
 
**Consider:**


**Source:** 

Stephen Finbow and Gary MacGillivray, 


**Reference:** 
