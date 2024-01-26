Tags :
Zettel :  20240126-1439
Status : #triage 

-----

# 2P2N-SAT to CFire reduction

**Previous note:** [[202401261303 bFire doesn't work]]

-----

### Questions & thoughts:

Consider the $2P2N$-SAT problem, a variant of 3-SAT for which in a formula $\phi$, every variable $x_i$ for $1\leq i \leq n, n\in \mathbb{N}$ occurs twice as a positive literal and twice as a negative literal. This is NP-complete - see [[202401261523 2P2N-SAT Complete]].

Instance of 2-2-SAT: variables $x_1, \dots, x_n$ and clauses $C_1, \dots, C_m$ in 3CNF composing a formula $\phi$. Question: is there a satisfying assignment of variables such that $\phi$ evaluates to true?

Construct a graph $G$ as follows. Starting from a single vertex (the root) labelled $r$, create $2n$ paths from $r$, each of length $n+2m$. For each path $P_i$ for $1\leq i\leq n$, label the vertex of degree 1 $v_i^+$ and for $n+1\leq i \leq 2n$, label the vertex $v_i^-$. Then, for the terminal (leaf) vertex of each path, add two further vertices only adjacent to the leaf, label one $C_j$ and the other $C_k$, which indicate the clauses in which the literal appears ($j$ and $k$ need not be distinct). Now, let the budget $b$ be 2 and define a cost function over the vertices of $G$ as follows:
$$
c(v, t)=\begin{cases}
2 &\textrm{if } v \textrm{ is labelled literal } x_i \textrm{ and } t=i\\
1 &\textrm{if } v \textrm{ is labelled clause } C_j \textrm{ and } t=n+2j-2 \textrm{ or } t=n+2j-1\\
3 &\textrm{otherwise}
\end{cases}
$$

In particular, this means that we can only defend either the vertex labelled $v_i^+$ or $v_i^-$ at time $1\leq i \leq n$ and we can defend two clause vertices labelled $C_j$ at time $n\leq j \leq 2n$.

What is my final argument here? Maybe:

2P2N-SAT yes $\iff$ defend all of the clause-labelled vertices $\iff$ defend at least $n+m$ vertices?


-----
 
**Consider:**


**Source:** 


**Reference:** 
