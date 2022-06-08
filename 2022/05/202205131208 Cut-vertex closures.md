Tags :
Zettel :  20220513-1208
Status : #triage 

-----

# Cut-vertex closures

**Previous note:** [202205131153 Pre-processing graphs](202205131153%20Pre-processing%20graphs.md)

-----

### Questions & thoughts:

Surprising table in the Kiss paper that I'd like to reproduce numbers/expressions for:

| Number of vertices in Path |  NFS  |  RS   | 
| ----- | ----- | ----- |
| 3 | 13    | 10    |
| 4 | 23   | 12 |
| $n$ | $(3n^2-n+2)/2$   | 5n-3 |

**Star-triangle network**

Triangles labelled $i=1, 2, \dots, M$ around a central vertex $1.$ The external vertices (i.e. the two vertices other than the central vertex in each triangle) are labelled $i_1$ and $i_2.$ 

An individual triangle needs 18 equations (6 singles, 6 doubles, 6 triples) but when a triangle is part of a larger network, we may need more, e.g. since the central node is a _cut-vertex,_ we will require some equations for $SS$-edges and $SSS$-triples to account for infection from outside of the triangle. In fact, for the star-triangle we will require 2 extra equations for edges and 1 for triples. We don't require an equation for $\langle S_{i_1}S_{i_2}\rangle$ is not required as this can't become infected from the outside.

In summary: reduced system appears to require $(18+2+1)M = 21M$ equations (18 for each triangle as an individual, plus an extra 2 for $SS$-edges and 1 for an $SSS$-triple). However, the cut-vertex has been over-counted $M$ times in each of those $M$ triangles in single equations, meaning $\langle S_1 \rangle$ and $\langle I_1 \rangle$ have appeared $M$ times but need only appear once. Hence, the actual number of equations required here is: $21M-2(M-1)=19M+2.$

The precise closures used for the star triangle network are:

$$
\begin{align}
\langle S_1 S_{i_1}S_{i_2}I_{k_j}\rangle\langle S_1 \rangle&=\langle S_1 S_{i_1} S_{i_2} \rangle\langle S_1 I_{k_j} \rangle\\
\langle S_1 S_{i_1} I_{k_j}\rangle\langle S_1 \rangle&=\langle S_1 S_{i_1} \rangle\langle S_1 I_{k_j} \rangle\\
\langle S_1 S_{i_2} I_{k_j}\rangle\langle S_1 \rangle&=\langle S_1 S_{i_2} \rangle\langle S_1 I_{k_j} \rangle\\
\langle S_1 S_{i_1} I_{i_2} I_{k_j}\rangle\langle S_1 \rangle&=\langle S_1 I_{i_1} S_{i_2} \rangle\langle S_1 I_{k_j} \rangle\\
\langle S_1 I_{i_1} S_{i_2} I_{k_j}\rangle\langle S_1 \rangle&=\langle S_1 I_{i_1} S_{i_2} \rangle\langle S_1 I_{k_j} \rangle
\end{align}
$$
for $i, k=1,2,\dots,M, i\neq k, j=1,2.$ 

-----
 
**Consider:**

- Try to reproduce expression for number of equations for a path on $n$ vertices for both NFS and RS
	- Looks as though the tuples we thought we needed equations for when considering paths may be incorrect (specifically, tuples of full path length)


**Source:** 


**Reference:** 
