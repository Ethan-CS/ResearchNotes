Tags :
Zettel :  20220628-1830
Status : #triage 

-----

# Counting Number of Equations for an SIR Model on a Cycle Graph

**Previous note:** [202206281827 Master Equation](202206281827%20Master%20Equation.md)

-----

## Statement to prove

Proposition: the number of equations required to describe an $SIR$ model on a cycle graph on $n$ vertices is given by $3n^2-3n$.

## Prerequisites

- Master equation for deriving equations for (sub)system states
    - Info: [Master Equation](obsidian://open?vault=ResearchNotes&file=2022%2F06%2F202206281827%20Master%20Equation)
    - Source[^1]

## Proof

We begin by observing that we require $2n$ equations for singles: for an $SIR$ model, we require an equation for each of $n$ vertices being susceptible and each vertex being infected. 
For doubles, we require equations for $n$-many pairs of adjacent vertices (by the definition of a cycle) being in two different states ($SI$ and $IS$), so we require $2n$ equations for two-vertex terms in total. 
Then, for each $l$-length term when $l\geq 3$, we have two cases to consider. If $3\leq l < n$, we observe that $3n$-many $l$-vertex states are required. There are $(n-3)$-many such terms containing $l$ vertices. 
We also observe that we require $2n$-many equations for terms on $n$ vertices. In total, we therefore have $6n+3n(n-3)=3n^2-3n,$ as required.




[^1]: Kieran J. Sharkey, _Deterministic epidemic models on contact networks: Correlations and unbiological terms,_ Theoretical Population Biology, Volume 79, Issue 4, 2011, pp. 115-129
[^2]: Istvan Z. Kiss, Charles G. Morris, Fanni Sélley, Péter L. Simon Robert R. and Wilkinson, *Exact deterministic representation of Markovian SIR epidemics on networks with and without loops*, Journal of Mathematical Biology, 2014, 70 (3), pp. 437-464