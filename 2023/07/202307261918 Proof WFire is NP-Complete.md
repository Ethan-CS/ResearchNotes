Tags : #proof #WFire
Zettel :  20230726-1918
Status : #triage 

-----

# Proof: WFire is NP-complete

**Previous note:** [202307261253 Firefighter Motivation](202307261253%20Firefighter%20Motivation.md)

-----

### Questions & thoughts:

Below has been moved from Overleaf doc to here as proof is more for my own practice than anything anyone would be interested in reading.

We show that **WFire** is NP-complete by first proving the following by reduction from **Firefighter**:

*Lemma:* ***WFire** is NP-Hard.*

Proof.

Consider an instance of **WFire** on a rooted graph $(G, r)$, an integer $k\geq1$, a cost function $c$ defined as $\forall v\in V,\,c(v) = 1$ and a budget $b=1$.

In this instance of **WFire**, protecting any vertex has a cost of one. Since the protection budget per time-step is also one, only a single vertex (no matter the choice) can be defended at each time-step, as in **Firefighter**. We have clearly encoded **Firefighter** into an instance of **WFire**, meaning **WFire** is NP-Hard since **Firefighter** is known to be NP-hard.

End of proof.


To show that **WFire** is NP-complete it remains only to show that it is contained in NP.

Theorem: **WFire** is NP-complete.

Proof.

Consider a certificate $(F, D)$ where $F$ and $D$ are sequences of vertex sets $f_i$ and $d_i$ containing the vertices to which the fire has spread at time $i$ and the vertices defended at time $i$ respectively. Clearly, $|F|+|D|\leq|V(G)|$ and $|\bigcup F|+|\bigcup D| = |V(G)|$ as no more than $|V|$ vertices can be burned or defended. Since both $F$ and $D$ are the same size (the number of time-steps), they are both of maximum size $|V|/2.$ Thus, the certificate $(F, D)$ is polynomial in the size of the input.

To verify that the certificate is valid, we verify the following in time polynomial in the size of the certificate:
1. For each $i$, the sum of $\texttt{cost}(v)$ over all $v\in d_i$ is at most $b$,
2. For each time $t=i,$ each vertex $v\in d_i$ is neither burned nor defended,
3. At the end of the process, no undefended vertex is adjacent to a burning vertex.

We first verify part (1) of the question of **WFire** for a certificate $(F, D),$ that the sum of the costs to defend each vertex in each defensive step does not exceed the defence budget $b.$ First, we iterate over $i$ to calculate $\sum_{i=1}^{|d_i|}\texttt{cost}(v)$ for all $v\in d_i,$ which we have shown requires at most $|V|/2$ iterations, and verify that the sum is less than $b.$ Hence, part (1) can be verified in time polynomial in the size of the input.

Now, we check part (2): at each time-step $i,$ each vertex $v\in d_i$ is neither burned nor defended (so is eligible for defence). For this, we iterate over $i,$ which we again note is at most $|V|/2,$ and then verify that each $v\in d_i$ does not appear in any previously burned vertex set i.e., for each $v\in d_i$ check that $v\notin d_j$ and $v\notin f_j$ for $j=1, \dots, i-1$. 
// In the same iteration, for each $v\in d_i$ we verify that it is not adjacent to a burning vertex $w\in\bigcup_0^{i-1} F$ in the previous timestep.
This verification can therefore also be completed in time polynomial in $|V|.$

To check part (3), that at time $T$ no undefended vertex is adjacent to a burning vertex, we first iterate over $F$ and $D$ (which takes no more than $|V|/2$ iterations) to get two lists of all burned and all defended vertices. Then, we get a list of all vertices not contained in either by iterating over all $|V|$ vertices in the graph and checking whether they are in either list (which can be done in $O(n^2)$ time) and, for any of the $|V|$ vertices remaining neither burned nor defended (if any), we check their neighbours and verify that none of them are in the list of burning vertices (also $O(n^2)$ in the worst case). Hence, this third part can be verified in time polynomial in the size of the input.
To verify that $k$ or more vertices are saved at the end of time $T.$ For this, we simply take the list of neither burned nor undefended we obtained in verifying (3) and compute the length (which takes $O(n)$ time) and verify that this is greater than or equal to $k.$ Thus, this final part of the question can also be computed in time polynomial in the size of the input.

Hence, having shown that - given a certificate $(D, F)$, which we have shown is polynomial in the size of the graph $G$ - the question for **WFire** can be answered in time polynomial in the size of the graph $G,$ meaning that **WFire** is contained in NP. In particular, having shown in the above lemma  that **WFire** is also NP-Hard, we have shown that **WFire** is NP-complete.

End of proof.



-----
