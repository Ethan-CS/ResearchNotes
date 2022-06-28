Tags : #Proof #Lemma #Results
Zettel :  20220628-1759
Status : #triage 

-----

# Expression for Number of Subpaths in a Path

**Previous note:** [202206281754 Num Eqns SIR on Path](202206281754%20Num%20Eqns%20SIR%20on%20Path.md)

-----

## Statement to prove

Proposition: for a path on $n$ vertices, the number of subpaths on $l\leq n$ vertices is $n-(l-1)$.

## Proof

Consider a path graph $P_n$ on $n$ vertices. We proceed inductively. Subpaths of length $l=1$ are single vertices, of which there are clearly $n$-many. By the result, we should expect $n-(1-1)=n$ and so the base case of $l=1$ holds.

Now, for some $k<n$ assume that there are $n-(k-1)$-many $k$-length subpaths in $P_n$. We note that there is a single $k$-length subpath containing the vertex $v_n$, which has vertices $\{v_{n-k+1},v_{n-k+2},\dots,v_n\}$. In a similar way, the single $(k+1)$-length subpath containing $v_n$ has vertices $\{v_{n-k},v_{n-k+1},\dots,v_n\}$. This means the lowest-indexed vertices in all $(k+1)$-length paths are $\{v_1,v_2,\dots,v_{n-k-2}, v_{n-k}\}$, meaning there are $n-k=n-((k+1)-1)$ paths of length $k+1$, as expected.

Hence, having shown the result is true in the base case of $l=1$ and that assuming the result is true for $l=k$ implies it is true for $l=k+1$, by the principle of mathematical induction we have proven the result in general.


QED.