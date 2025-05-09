Tags :
Zettel :  20240816-1357
Status : #triage 

-----

# Feedback by section

**Previous note:** [[202408022045 ALGOWIN Rejection]]

-----

### Overall Writing

Please avoid using references as grammatical objects ("in [X]"). Instead, either tack them at an appropriate point of the sentence without referring to them (e.g."the problem is known to be NP-hard [X]"), or name the authors ("Y et al. prove that the problem is NP-hard [X]").

I find it much easier to navigate a paper when counters for statements (theorems, lemma, etc) are:  
 + unified (no Theorem 1 and Lemma 1, rather each number is only assigned to a single statement)  
 + separated by section (so the first statement in Section 3 is Theorem/Lemma/... 3.1)  

Whenever possible, make an effort to separate the preconditions and inputs  
 from the statement of the lemma/theorem, or the definition.   

Please use \emph in definitions to introduce new terms.  

You use the variable T in at least 3 different ways: as a tree, as an interval in Def. 2, and as a time step later on. Please avoid this mixing.  

### Overall Structure

The writing of the paper should be thoroughly revised for readability. In particular the paper should be more structured, with different types of content (motivation, related work, own contributions, techniques) separated into logical sections.

Figures are usually set as floats on the top or bottom of the page, without text wrapping around them. In certain exceptional cases, they can be placed on the side of the page, but I would say that they should be on the outside edge and in close proximity to the relevant content.  

### Abstract

In the abstract, start by presenting the firefighter problem, as it is not clear that the reader knows it. 

Also in the abstract, it is common to separate the results into a different paragraph

### Related Work

I would like to see a much more expanded section on related work. FF and related problems have a vast collection of works, including minimization and maximization versions, approximation, etc.  

### Contribution

I recommend including formal theorems in the Contributions section (Sec 1.1)  
 so the reader can immediately see a collection of the results proved in your  
 paper (and can judge, just from the Introduction, if they want to read the  
 technical content).
### Preliminaries

In page 1-2, the whole paragraph starting with "We first give graph theoretic", as well as the formal definition of the problem (in the box) should be moved to a Preliminaries section. In fact, most things in the paragraph could be omitted, since they are standard graph notation.

In Def. 2, you could define Fraktur S as the current co-domain of the functions S_{I, sigma}, and define those as going to Fraktur S. So, Fraktur S = {((v1, x), (v2, x), . . . , (vn, x)) | x ∈ {burning, defended, open}, S_{i, sigma}: [0, |sigma] -> Fraktur S .

You could also define Fraktur S simply as {b,d,o}^V(G), which simplifies it by avoiding the numbering of vertices. Regardless, a formal definition of Fraktur S is necessary.  

Please define "feasible strategy" as a sigma satisfying all of the constraints of CFire, so you can simplify the definitions. 

The cost function c is introduced as a function with three arguments (a vertex, a time step, and a state), but often used with other arguments (e.g. c(v) or c(v,state)). It would be better to explicitly say that you write static cost functions as c(v), state-dependent ones as c(v,state), etc.  

In Definition 1, you could write:  
   "Let I be an instance of CFire with budget b on a graph G = (V,E).  
   A \emph{strategy} is a sequence...",  
   with the 2nd line on a different paragraph.  
   This allows the reader to immediately jump to the definition and refer to  
   the inputs only if needed.  
 + Similarly for Def. 2, you could start width  
   "Let I be an instance of CFire on a graph G, with vertices v1... Let sigma be a strategy for I."  
 + The same applies to theorems such as Theorem 4:  
   "Consider a PathContainable instance for CFire, composed of a rooted tree..."  
   "Then, its cost function assigns..."  

page 3, Definition 2: The definition of the mapping S_{I,sigma} only allows tuples in which all vertices are paired with the same value x; this is not what you want, you need to allow each vertex to be paired with an arbitrary value in {burning,defended,open}, independent of the other vertices. Also, it is ambiguous whether the function S_{I,sigma}(i) returns the state before or after the verties in sigma_i have been defended in step i.  

The function S_{I,sigma} is introduced as a mapping from time steps to states in Definition 2, but then the rest of the paper uses a function S (that hasn't been defined but is presumably meant to be S_{I,sigma}) with many different types of arguments:  
- In the definition of CFIRE on page 4 you use S(i,sigma{i-1}), a function that depends on the time step i and the vertices defended in step i-1: What you need is the state of the network a time i (which could be obtained by S_{I,sigma}(i) or S_{I,sigma}(i-1) depending on the definition.  
- In Example 3 and 4 on page 5, you write S(t,{d_1^1,...,d_t^{r_t}}), a function that depends on the time step t and the set of all vertices defended from time 1 to time t (ignoring in which time step which vertex is defended). Again, this does not correspond to the definition of S_{I,sigma}. Besides, I don't think the vertices defended at time t should be allowed to have an influence on the cost of defending a vertex at time t.  

The paragraph "For an instance of CFire" in page 4 would feel more natural  
 in the introduction, to show the different uses of your problem.   
 The same could be said of the discussion on how state-dependent functions  
 can model behaviours in an epidemic.  

### Results

page 6, first paragraph: you claim that assigning burning to all the open neighbours of the burning vertices at time i-1 takes O(n) operations. If we do this by iterating over all neighbours of all burning vertices, this would take O(m) rather than O(n) time.  

I feel like Lemma 1 and Theorem 1 are not really necessary. Regarding Lemma 1, I expect that the audience of the conference will be able to show that CFire is in NP. For Theorem 1, it can be replaced by a sentence saying that CFire directly generalises Fire when b=1 and costs are uniform and 1.  

The sentence "As k is already a variable in CFire, ..." in page 10 is not necessary, it is quite clear what the \ell in P_\ell-free graphs means (though you should probably clarify that it refers to *induced* paths).  

Please clarify that your algorithm is FPT by *a combination of* the three parameters, as it could be understood as FPT algorithms for each of them.  

You can alternatively say that it is FPT by the sum of treewidth, budget   
 and maximum time step.  
 
 You should also be more formal in Thm 10 and write "FPT parameterised by  "tw + b + T", which clarifies the issue.

I find the summary of the paper in Section 3 unnecessary, as we are not talking about a >100 page document, and the same things are said in the Introduction. You can keep the open problems / conjectures part, but moving it to the Introduction would also be perfectly fine.

You should just put both Figure 2 and 3 at the top or bottom of the page (possibly even combined into a single figure!), but if you insist on placing them in text (and the publisher allows it), Fig. 2 should be on the right, and Fig. 3 should be within the proof of Thm 3.  

page 6-7: The proof of Theorem 2 has many issues:  
You label the terminal vertices v_i+ for i=1..n and v_i- for i=n+1..2n, but later you assume that for i=1..n you have v_i+ and v_i-. To achieve this, you would need to label the terminal vertex of P_i for i=n+1..2n with v_{i-n}-, not with v_i-.  
You write that C_i and C_{i-1} have cost 1 at time i for i=n+1..2n. This would indicate that we have vertices C_i for i=n..2n. However, we have m=4n/3 clauses numbered from C_1 to C_m, which doesn't match the clauses referred to here. Besides, to make the proof work, I think you need that the vertices of clause i can be defended in 2 consecutive time steps, so to make the proof work you should probably specify that the three vertices corresponding to C_i are active in step n+2i-1 and n+2i, or something like this.  
You claim "we save a further m vertices", but the n literals defended in steps 1..n always save a further 2n vertices (as each such literal saves its two children).  
"restricts us to defending at mos ttwo of the three associated vertices": associate to what?  
  
page 8, proof of Theorem 3: The formulas given in the proof are clearly wrong: For example, for T=1, it is clear that l+1 vertices can be saved, but the formula gives (l^2+l)/2+2T=(l^2+l)/2+2, which can be much larger than l+1.  
  
page 8, Definition 3: The definition should make clear that it is about instances on the rooted tree (T,r) and should say clearly whether the cost function must be static (as implied by the use of c(u) to refer to the cost of vertex u) or not  
  
page 9, Theorem 4: The rooted tree with three vertices (a root r with two children u and v) with costs c(r)=1,c(u)=2 and c(v)=3 and budget b=3 seems to be a counterexample to the claim of the theorem. The proof assumes that one can put a burning vertex next to v1 but none in the neighborhood of v2, but this is not always possible (see my counterexample).  
  
page 9: The definition of "defensible" is unclear: Does it mean defending all its neighbours, or only all its neighbours except the one that may be burning at the moment?  
  
page 9: Strategy 1 is unclear: "all Delta-1 open vertices adjacent to fire not on the path": Why are there exactly Delta-1 (and not possibly fewer) such open vertices? Besides, the formulation could be made clearer.  
  
page 11, "parameterized by the length of the longest path in the graph, budget and maximum time": Why is maximum time needed? The running-time of Theorem 8 is FPT in the first two parameters already.  
  
page 11: You claim running-times involving n^b for cographs and n^{2b} for split graphs, but with l=4 and l=5 the term n^{b(l-2)} from Theorem 8 would give n^{2b} and n^{3b} instead.  
  
page 11: The formulation "if there is a tree decomposition" is very odd. If a graph has bounded treewidth, then there must be a tree decomposition, of course.  

### Appendix

page 14, proof of Theorem 7: Creating a mapping M that is effectively the same as the given cost function seems unnecessarily indirect. "at the end of 1" should probably be "at the end of step 1".  
  
page 15, Procedure 1:  
line 4-5: The for-loop should probably exclude the parent node (which is already burning).  
line 10-11: The return results of the recursive calls are ignored, so the function doesn't produce any result.  
  
page 15, Procedure 2: The code refers to values d[2] and d[3] that have not been defined. In steps 7-12, it is not clear why we don't always defend v instead of its neighbours: If we defend v, then its neighbours are automatically saved, but if we defend only its neighbours, then v will get burned.  
  
page 16, paragraoh "Since the process ends": You claim that the formula Saved(...) ensures that no vertex is defended more than once and the sum of the costs of the vertices selected does not exceed the budget; but these properties are only ensured by the final predicate introduced in the following paragraph.  
  
page 16, formula for ValidStrat: The formula refers to S_{V,i}, which has not been defined. The formula uses \forall sigma_i in sigma, but sigma has been defined as a set at the start of Appendix C, so its elements are vertices not sets of vertices. The final term "forall tau in sigma require d!=d' for all d in sigma_i and d' in sigma" would always evaluate to FALSE as vertices in sigma_i will be in both sigma_i and tau (for the choice tau=sigma_i in sigma).  


-----
 
**Consider:**


**Source:** 


**Reference:** 
