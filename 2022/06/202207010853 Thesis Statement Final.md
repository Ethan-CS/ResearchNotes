# Thesis Statement

## Introduction

I am pursuing two threads of research over the next year, one related to agency-characteristics modelling from the first year of research and another from the more recent work on dynamical compartmental graph models of disease. My aim is to identify common themes and areas for comparison in these two strands to form a cohesive narrative in the final thesis.


### Modelling Agency Characteristics

We will study the application of interventions to control disease that exploit modelled agency characteristics of nodes in a graph. We expect to find that intervention strategies based on max-weight clique algorithms will perform better than implementations of simple heuristics based on degree and distance-to-infection.  


### Dynamical Modelling Approach

We predict that exact dynamical compartmental graph models of disease without graph decomposition will computationally out-perform stochastic compartmental graph models of disease only for small graphs or when a very large range of initial conditions are to be considered, for instance in understanding an emerging disease for which little precise epidemiological data is available.

We prove that, in the worst case, the number of equations required for an exact description of a compartmental graph model is exponential in the number of vertices. We will prove that the number of such equations for a graph with polynomially many connected subgraphs is polynomial in the number of vertices (and exponential in the number of model compartments, but this is not asymptotically limiting to this modelling approach).

We show that the dynamical modelling approach exhibits acceptable computational performance on larger graphs with single vertex cut-sets (such as paths, caterpillars, trees and sparse Erdős–Rényi graphs) when the closure result from Kiss et al.[^1] is implemented, because the numbers of equations required with this result is polynomial in the number of vertices for such graphs.

We will generalise the result in Kiss et al.[^1] to larger clique cut-sets so that the dynamical approach exhibits acceptable performance on larger graphs with small vertex cut-sets.

----
## Bullet-point version

### Modelling Agency Characteristics

- I will study the application of disease-control interventions that include agency information, implementing both a max-weight clique approach and simple heuristic approaches, and I expect to find that:
    - max-weight clique approaches will out-perform simple heuristics.

### Dynamical Modelling Approach

Concerning exact dynamical compartmental graph models of disease:
- I will test the practical run-time of these models without graph decomposition, and expect to find:
    - they will out-perform stochastic compartmental graph models of disease only for small graphs or when a very large range of initial conditions are to be considered.
- I have proved that the number of equations required for an exact description of such a model is exponential in the number of vertices in the worst case. 
    - I will prove that the number of equations when the contact graph has polynomially-many connected subgraphs is polynomial in the number of vertices.
- I will show that this modelling approach exhibits acceptable computational performance on larger graphs with certain structural properties. Specifically:
    -  it exhibits acceptable performance on graphs with single vertex cut-sets (e.g. paths, caterpillars, trees and sparse Erdős–Rényi graphs) when the closure result from Kiss[^1] is implemented.
    -  This is because the numbers of equations required with this result is polynomial in the number of vertices for such graphs.
- I will generalise the result in Kiss[^1] to larger clique cut-sets so that the dynamical approach exhibits acceptable performance on larger graphs with small vertex cut-sets.

----

[^1]: I. Z. Kiss, C. G. Morris, F. Sélley, P. L. Simon, and R. R. Wilkinson, _Exact deterministic representation of markovian SIR epidemics on networks with and without loops,_ Journal of Mathematical Biology, 70 (2014), pp. 437–464.
