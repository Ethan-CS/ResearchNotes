Tags : #Proof #Theorem #Results
Zettel :  20220628-1754
Status : #triage 

-----

# Counting Number of Equations for an SIR Model on a Path Graph

**Previous note:** [202206281607 Short biography](202206281607%20Short%20biography.md)

-----

## Statement to prove

Proposition: the number of equations required to describe an $SIR$ model on a path graph on $n$ vertices is given by $(3n^2-n+2)/2.$

## Prerequisites

- Proof that the number of subpaths on $l$ vertices in a path on $n\geq l$ vertices is given by $n-(l-1)$.
    - Proof: [sub-paths result](obsidian://open?vault=ResearchNotes&file=2022%2F06%2F202206281759%20Num%20Subpaths%20Result)
- Master equation for deriving equations for subsystem states
    - Info: [Master Equation](obsidian://open?vault=ResearchNotes&file=2022%2F06%2F202206281827%20Master%20Equation)
    - Source[^1]

## Proof


Consider an $SIR$ model on a path graph on $n$ vertices. Consider first the equations for singles. We require an equation for each of $n$ vertices being in states $S$ and $I,$ hence there are $2n$ equations for singles. These equations contain terms for which we also require equations in the system.

In the case of equations for a vertex $i$ being in state $S,$ from the master equation this will introduce terms of the form $\langle S_i I_j \rangle$ and/or $\langle I_h S_i \rangle$ for vertices $h$ and $j$ adjacent to $i.$ That is to say, we require two equations for each adjacent pair of vertices $(i, j):$ $\langle S_i I_j \rangle$ and $\langle I_i S_j \rangle.$ There are $n-1$ pairs of adjacent vertices in a path, so in total we require $2(n-1)$ equations for tuples of length two.

For $n\geq3$, these equations produce further terms that require equations. In the case of two-vertex-state terms of the form $\langle S_i I_j \rangle,$ from the master equation the only subsystem state that could lead to this state is of the form $\langle S_i S_j I_k \rangle$ for a vertex $k$ adjacent to $j$ (and this, of course, is only required if such a $k$ exists). States of the form $\langle S_i I_j \rangle$ would be exited (1) by the recovery of $j$ and (2) by the infection of $i$ by $j,$ but also (3) by external infection of $i$. The cases of (1) and (2) do not lead to new terms, but (3) leads to terms of the form $\langle I_h S_i I_j \rangle$ where $h$ is a vertex adjacent to $i$ (if such a vertex exists). For tuples of the form $\langle I_i S_j \rangle,$ the entry subsystem state is $\langle I_h S_i S_j \rangle$ for a vertex $h$ adjacent to $i$. Other terms are of forms already considered in the case of states of the form $\langle S_i I_j \rangle$. Hence, all required tuples of length three for an $SIR$ graph on a path of length $n$ have states in the orders $SSI$, $ISS$ and $ISI$ on subpaths of length three. There are $(n-2)$-many subpaths of length three (i.e., sets of vertices $(i, j, k)$ where $i$ is adjacent to $j$ and $j$ is adjacent to $k$) hence there are $3(n-2)$ equations for tuples of length three.

For tuples of length $l$, where $2<l\leq n$, the number of equations is given by $3(n-(l-1))$. This is because, by analogous arguments to the case of $n=3$, the equations for tuples of length $l-1$ include three state combinations for tuples of length $l$. In particular, these are terms of the form $\langle S_i S_{i+1} \dots I_{i+(l-1)} \rangle$, $\langle I_i S_{i+1} \dots S_{i+(l-1)} \rangle$ and $\langle I_i S_{i+1} \dots I_{i+(l-1)} \rangle$ and the number of sub-paths of length $l$ on a path is given by $(n-(l-1))$.

Hence, the total number of equations for a path on $n$ vertices is given by

$$
\begin{align}
2n + &2(n-1) + 3\sum^n_{i=3}(n-(i-1))\\
& = 4n-2+3\left(\sum_{i=3}^nn-\sum_{i=3}^ni+\sum_{i=3}^n1\right)\\
& = 4n-2+3((n-2)+(n^2-2n)-(n(n+1)/2-3))\\
& = \frac{1}{2}(3n^2-n+2)
\end{align}
$$
which is precisely the result reported by Kiss et al.[^2] for the number of equations for an $SIR$ model on a path graph on $n$ vertices.  $\blacksquare$


[^1]: Kieran J. Sharkey, _Deterministic epidemic models on contact networks: Correlations and unbiological terms,_ Theoretical Population Biology, Volume 79, Issue 4, 2011, pp. 115-129
[^2]: Istvan Z. Kiss, Charles G. Morris, Fanni Sélley, Péter L. Simon Robert R. and Wilkinson, *Exact deterministic representation of Markovian SIR epidemics on networks with and without loops*, Journal of Mathematical Biology, 2014, 70 (3), pp. 437-464
