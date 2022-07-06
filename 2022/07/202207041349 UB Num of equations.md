Tags :  #Proof #Bound #Counting 
Zettel :  20220704-1349
Status : #triage 

-----

# UB on Number of Equations

**Previous note:** [202206281830 Num Eqns SIR Cycle](202206281830%20Num%20Eqns%20SIR%20Cycle.md)

-----

Upper bound on number of equations in system describing a compartmental model $M$ with $s$ states on a graph $G$ on $n$ vertices:

There are $n\choose i$ ways to combine $i$ vertices and $s^i$-many permutations of states of length $i$. Then, the number of equations for terms with $i$-many vertex locations is bounded above by ${n\choose{i}} s^i$. Hence, in total we have
$$
\begin{align*}
  \sum^n_{i=1} {n\choose i} s^i &= \sum^n_{i=0} {n\choose i} s^i - 1 \\
  &= (s+1)^n-1
\end{align*}
$$
using the summation formula $\sum^n_0{n\choose i}a^{n-i}b^i=(a+b)^n$.

Hence, the number of equations in a system describing (...) is *exponential* in the worst case.

-----
