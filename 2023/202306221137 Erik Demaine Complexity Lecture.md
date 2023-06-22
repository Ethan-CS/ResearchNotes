Tags :
Zettel :  20230622-1137
Status : #triage 

-----

# Erik Demaine Complexity Lecture Notes

**Previous note:** [202306211446 Satisfiability](202306211446%20Satisfiability.md)

-----

### Questions & thoughts:

#### Recap

 - P - problems solvable in poly time
 - NP - decision problems solvable in _nondeterministic_ poly time

Nondeterministic: we can guess one out of poly many options in $O(1)$ time: if any guess can lead to YES then we get such a guess. CO-NP is same but with NO. No gives lots of information - means there are no paths leading to a YES, but YES only tells you at least one path leads to a YES.

3SAT: given a boolean formula of the form $(x_1 \vee x_2 \vee \neg x_6) \wedge (\neg x_2 \vee x_3 \vee x_7)$, can you set the variables $x_1, x_2, \dots \rightarrow \{T, F\}$ such that the formula evaluates to TRUE?

There is no Poly time algorithm but there is a Nondeterministic-poly time algorithm. 
$\in$NP: guess $x_1$ T or F, then $x_2,$ etc. All constant time guesses. If this all comes out true, return YES, otherwise return NO.

We can think of this as a verification algorithm: given a satisfying assignment, we can check this in poly time in size of formula. This is an easy way of checking YES, does not mean there is a way to check NO (there isn't a way to do this here).

Another definition of NP: decision problems with poly size certificates and poly time verifiers for YES instances.

#### NP-Completeness

 - $X$ is **NP-Complete** if $X$ is in NP and $X$ is *NP-Hard*.
 - $X$ is **NP-Hard** if every problem $Y\in$ NP *reduces* to $X$.
 - **Reduction** for a problem $A$ to a problem $B$ is a poly time algorithm converting $A$ inputs into equivalent $B$ inputs.
 - X is not in P unless P=NP.

NP-Complete - you're _exactly_ as hard as everything in NP, no easier no harder.

```
----------> difficulty
P
|----|---|
NP   | NP-Hard
     NP-Complete
```


-----
 
**Consider:**


**Source:** 


**Reference:** 
