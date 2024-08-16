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


### Preliminaries

In page 1-2, the whole paragraph starting with "We first give graph theoretic", as well as the formal definition of the problem (in the box) should be moved to a Preliminaries section. In fact, most things in the paragraph could be omitted, since they are standard graph notation.

In Def. 2, you could define Fraktur S as the current co-domain of the functions S_{I, sigma}, and define those as going to Fraktur S. So, Fraktur S = {((v1, x), (v2, x), . . . , (vn, x)) | x ∈ {burning, defended, open}, S_{i, sigma}: [0, |sigma] -> Fraktur S .

You could also define Fraktur S simply as {b,d,o}^V(G), which simplifies it by avoiding the numbering of vertices. Regardless, a formal definition of Fraktur S is necessary.  

Please define "feasible strategy" as a sigma satisfying all of the constraints of CFire, so you can simplify the definitions. 

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

The paragraph "For an instance of CFire" in page 4 would feel more natural  
 in the introduction, to show the different uses of your problem.   
 The same could be said of the discussion on how state-dependent functions  
 can model behaviours in an epidemic.  

### Related Work

I would like to see a much more expanded section on related work. FF and related problems have a vast collection of works, including minimization and maximization versions, approximation, etc.  

### Contribution

 I recommend including formal theorems in the Contributions section (Sec 1.1)  
 so the reader can immediately see a collection of the results proved in your  
 paper (and can judge, just from the Introduction, if they want to read the  
 technical content).

   
### Results

I feel like Lemma 1 and Theorem 1 are not really necessary. Regarding Lemma 1, I expect that the audience of the conference will be able to show that CFire is in NP. For Theorem 1, it can be replaced by a sentence saying that CFire directly generalises Fire when b=1 and costs are uniform and 1.  

The sentence "As k is already a variable in CFire, ..." in page 10 is not necessary, it is quite clear what the \ell in P_\ell-free graphs means (though you should probably clarify that it refers to *induced* paths).  

Please clarify that your algorithm is FPT by *a combination of* the three parameters, as it could be understood as FPT algorithms for each of them.  

You can alternatively say that it is FPT by the sum of treewidth, budget   
 and maximum time step.  
 
 You should also be more formal in Thm 10 and write "FPT parameterised by  "tw + b + T", which clarifies the issue.

I find the summary of the paper in Section 3 unnecessary, as we are not talking about a >100 page document, and the same things are said in the Introduction. You can keep the open problems / conjectures part, but moving it to the Introduction would also be perfectly fine.

You should just put both Figure 2 and 3 at the top or bottom of the page (possibly even combined into a single figure!), but if you insist on placing them in text (and the publisher allows it), Fig. 2 should be on the right, and Fig. 3 should be within the proof of Thm 3.  
  


-----
 
**Consider:**


**Source:** 


**Reference:** 
