Tags :
Zettel :  20240126-1303
Status : #triage 

-----

# bFire doesn't work

**Previous note:** [[202401221212 Contribution section]]

-----

### Questions & thoughts:

Cut from the paper.

As motivation for the following section on tractability, we show that \bFire is tractable on graphs with a certain number of universal vertices but \CFire remains NP-hard on these graphs, even when restricted to static cost functions.
\begin{theorem}
    Instances of \bFire with budgets $b$ on graphs with $b+1$ universal vertices are solvable in time polynomial in the size of the instance.
\end{theorem}
\begin{proof}
     We consider separately the cases where $r$ is and is not a universal vertex.
     
     Assume first that $r$ is a universal vertex. Fire breaks out at $r$, then we can defend up to $b$ vertices. The fire then spreads to all other vertices and process ends at $t=1$. The question is therefore: $b\geq k$?
     
     Now assume that $r$ is not a universal vertex. Clearly, after fire breaks out our best option is to defend any set of universal vertices $\{v_1, \dots, v_b\}$. Fire then spreads to the remaining universal vertex. At the next time-step ($t=2$), we can defend $d\leq b$ remaining vertices (as many as possible up to $b$). The fire then burns every vertex still unburned and undefended. The question is therefore: $b+d\geq k$?

     In either case, the problem terminates after at most two time-steps and we clearly save the greatest possible number of vertices.
\end{proof}

\begin{theorem}
    Instances of \CFire with budgets $b$ on graphs with $b+1$ universal vertices are NP-complete even when restricted to static cost functions.
\end{theorem}
\begin{proof}
    To show the problem is NP-hard, we proceed by reduction from \bFire. Consider an arbitrary instance of \bFire on a graph $G=(V, E)$ and budget $b$; construct an instance of \CFire as follows. Let $G^\prime=(V^\prime, E^\prime)$ be the graph $G$ with $b+1$ universal vertices, which we denote by $U$. Let $c:V^\prime\rightarrow\mathbb{N}$ be a cost function defined for all $v\in V^\prime$ as follows:
    \begin{align*}
        c(v)=\begin{cases}
            1 &\textrm{if } v\in U,\\
            b+2 &\textrm{otherwise.}
        \end{cases}
    \end{align*}
    Set the budget of the instance of \CFire to $b+1 + b(b+2)$ so that, at each turn, we can defend all of the $(b+1)$ universal vertices (as each costs 1 to defend) and precisely $b$ non-universal vertices (as each costs $(b+2)$ to defend.
    By also setting the integer $k$ as in the instance of \bFire, we have constructed an instance of \CFire on a graph with $b+1$ universal vertices that can all be defended in the first time-step, leaving the rest of the game to proceed as an instance of \bFire with budget $b(b+2)$ (which can also be deployed in the first time-step) and cost to defend each vertex $(b+2)$. Hence, the constructed instance of \CFire is a yes-instance if and only if the arbitrary instance of \bFire is a yes-instance. Since \bFire is NP-hard by Theorem \ref{thm:b-firefighter-np}, \CFire is NP-hard even on graphs with universal vertices.
\end{proof}
This reduction works by de-coupling the budget and degree of the graph. By constructing a cost function that ensures the universal vertices can be defended cheaply and others as usual we can defend the universal vertices almost without consequence and the remaining problem proceeds on the remaining graph. In the following section, we see a way to re-couple these properties to give more natural cost functions that also allow otherwise hard instances of \CFire to be solved in time polynomial in the size of the input for particular graph classes.

-----
 
**Consider:**


**Source:** 


**Reference:** 
