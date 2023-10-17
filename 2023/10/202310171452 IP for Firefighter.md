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
&b_{x,0}=\begin{cases}
		     1 & \textrm{ if } x=r_i \textrm{ for some } i, 1\leq i \leq f\\
		     0 & \textrm{otherwise}
		 \end{cases}\\
& b_{x, t}, d_{x, t}\in \{0, 1\} & 1\leq t \leq T

\end{cases}
\end{align}
$$

**Explanation.** 
1. A vertex burning at time $t − 1$ is still burning at time $t$. 
2. A vertex defended at time $t-1$ is still defended at time $t$.
3. Every neighbour of a vertex burning at time $t−1$ is burning or defended at time $t$
4. No vertex can be both burning and defended at any time. 
5. A vertex with no burning neighbours at time $t − 1$ does not burn at time $t$. 
6. At most d firefighters are used per time step. 
7. Initialise the variables corresponding to time $t = 0$
8. Initialise the variables corresponding to time $t = 0$

Linear relaxation:
$$\textrm{max}\sum_{v\in V}d_vw(v)$$
subject to:
$$\
\begin{align}
\begin{cases}
&\displaystyle\sum_{\textrm{level}(v)=i}d_v\leq 1&\textrm{for each level }i\\
&d_v+\displaystyle\sum_{u\textrm{ an ancestor of }v}d_u\leq 1&\textrm{for every leaf } v \textrm{ of } T\\
&d_v\in\{0, 1\}&
\end{cases}
\end{align}
$$

Finbow and MacGillivray conjecture that there is a constant $c$ such that the optimum solution to the LP relaxation of the 0-1 integer program above is at most $c$ times the optimum integral solution i.e., linear programming gives a $c$-approximation algorithm for the Firefighter Problem on trees.

-----
 
**Consider:**


**Source:** 

Stephen Finbow and Gary MacGillivray, 


**Reference:** 
