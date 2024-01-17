Tags :
Zettel :  20240117-1028
Status : #triage 

-----

# Temporal Firefighter Definition

**Previous note:** [[202401171026 Monadic Logic]]

-----

### Questions & thoughts:

Another cut, a formal definition of TFire.

\begin{problem}
  \name{\textsc{Temporal Firefighter} (\TFire)}
  \instance{A rooted temporal graph $((G, \lambda), r)$ and an integer $k\geq 1$.}
  \question{Is there a strategy $\sigma=(d_1, d_2, \dots, d_T)$ for an integer $T$ such that if the fire breaks out at $r$:
    \begin{itemize}
        \item for each $d_i\in D,$ by time $i$ vertex $d_i$ is neither burned nor defended,
        \item after time $T$, no undefended vertex is adjacent to a burning vertex and
        \item at least $k$ vertices are unburned by time $T$?
    \end{itemize}}
\end{problem}
In a later reduction, we will rely on the following result.
The following result is surprising given \Fire is solvable in time solvable in the size of the input when restricted to cliques \cite{finbow_2009}.
\begin{theorem}\cite{hand_2022}\label{thm:temp-fire-clique}
    For any constant $c\in\mathbb{N}$, instances of \TFire restricted to rooted temporal graphs $((G=(V, E), \lambda), r)$ whose underlying graph is a clique and whose lifetime is at most $|V|^{1/c}$ are NP-complete.
\end{theorem}

-----
 
**Consider:**


**Source:** 


**Reference:** 
