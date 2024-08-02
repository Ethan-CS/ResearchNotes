Tags :
Zettel :  20240802-2045
Status : #triage 

-----

# ALGOWIN Rejection Notes

**Previous note:** [[202407041256 Current work]]

-----

### Questions & thoughts:

(My notes in *italics*)

#### Review 1

SUBMISSION: 18  
TITLE: Firefighting with defence costs  
AUTHORS: Ethan Hunter and Jessica Enright  
  
----------- Overall evaluation -----------  
SCORE: -2 (reject)  
----- TEXT:  
The paper introduces a new variation CFIRE of the firefighter problem where the cost of defending a vertex can depend on the vertex, the time step, and the current state of the graph (i.e. which vertices are burning, defended, or open). There is a budget b that can be spent on defending vertices in each step, and the question is to decide whether k vertices can be saved.  
  
The paper presents a number of results that are obtained largely by fairly straightforward adaptations of known results for the standard fire fighter problem or its budgeted variant. The biggest problem of the paper is that it is poorly written: Notation is used inconsistently, some proofs are not correct as stated, some claims are wrong. In its present form, the paper is not suitable for publication in my opinion. If the paper was very well written and all the proofs were convincing, I would have rated it as borderline.  

...
  
page 2: The paragraph starting with "In a game of CFIRE" describes b-FIRE, not CFIRE.  

*This is because that sentence is trying to motivate discussion of b-Fire, but doesn't achieve that clearly.*
  
page 3, Definition 2: The definition of the mapping S_{I,sigma} only allows tuples in which all vertices are paired with the same value x; this is not what you want, you need to allow each vertex to be paired with an arbitrary value in {burning,defended,open}, independent of the other vertices. Also, it is ambiguous whether the function S_{I,sigma}(i) returns the state before or after the verties in sigma_i have been defended in step i.  

*First fix - to check.*
  
The cost function c is introduced as a function with three arguments (a vertex, a time step, and a state), but often used with other arguments (e.g. c(v) or c(v,state)). It would be better to explicitly say that you write static cost functions as c(v), state-dependent ones as c(v,state), etc.  


  
The function S_{I,sigma} is introduced as a mapping from time steps to states in Definition 2, but then the rest of the paper uses a function S (that hasn't been defined but is presumably meant to be S_{I,sigma}) with many different types of arguments:  
- In the definition of CFIRE on page 4 you use S(i,sigma{i-1}), a function that depends on the time step i and the vertices defended in step i-1: What you need is the state of the network a time i (which could be obtained by S_{I,sigma}(i) or S_{I,sigma}(i-1) depending on the definition.  
- In Example 3 and 4 on page 5, you write S(t,{d_1^1,...,d_t^{r_t}}), a function that depends on the time step t and the set of all vertices defended from time 1 to time t (ignoring in which time step which vertex is defended). Again, this does not correspond to the definition of S_{I,sigma}. Besides, I don't think the vertices defended at time t should be allowed to have an influence on the cost of defending a vertex at time t.  
  
page 6, first paragraph: you claim that assigning burning to all the open neighbours of the burning vertices at time i-1 takes O(n) operations. If we do this by iterating over all neighbours of all burning vertices, this would take O(m) rather than O(n) time.  
  
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
  
page 14, proof of Theorem 7: Creating a mapping M that is effectively the same as the given cost function seems unnecessarily indirect. "at the end of 1" should probably be "at the end of step 1".  
  
page 15, Procedure 1:  
line 4-5: The for-loop should probably exclude the parent node (which is already burning).  
line 10-11: The return results of the recursive calls are ignored, so the function doesn't produce any result.  
  
page 15, Procedure 2: The code refers to values d[2] and d[3] that have not been defined. In steps 7-12, it is not clear why we don't always defend v instead of its neighbours: If we defend v, then its neighbours are automatically saved, but if we defend only its neighbours, then v will get burned.  
  
page 16, paragraoh "Since the process ends": You claim that the formula Saved(...) ensures that no vertex is defended more than once and the sum of the costs of the vertices selected does not exceed the budget; but these properties are only ensured by the final predicate introduced in the following paragraph.  
  
page 16, formula for ValidStrat: The formula refers to S_{V,i}, which has not been defined. The formula uses \forall sigma_i in sigma, but sigma has been defined as a set at the start of Appendix C, so its elements are vertices not sets of vertices. The final term "forall tau in sigma require d!=d' for all d in sigma_i and d' in sigma" would always evaluate to FALSE as vertices in sigma_i will be in both sigma_i and tau (for the choice tau=sigma_i in sigma).  
  
  
Minor typos:  
  
page 1: "to limits" -> "to limit"  
  
page 1: the closing parenthesis in "defence)" has no opening parenthesis that matches it  
  
page 5, Lemma 1: What is the "()" meant to be? Also, it should be stated clearly that you assume that the cost function oracle can be evaluated in constant time (even though the size of the arguments passed to it can be quite large, as a state has size n).  
  
page 6: "are no opern vertex" -> "are no open vertices"  
  
  
  
----------------------- REVIEW 2 ---------------------  
SUBMISSION: 18  
TITLE: Firefighting with defence costs  
AUTHORS: Ethan Hunter and Jessica Enright  
  
----------- Overall evaluation -----------  
SCORE: -2 (reject)  
----- TEXT:  
The firefighter problem (FIRE) is a one-player game on a graph, in which a (given)  
vertex starts burning, and on each turn, we are allowed to protect a  
non-burning vertex, after which the fire spreads from burning vertices to all  
of their non-protected neighbors (which become burning as well).  
  
In this paper, the authors introduce a generalization of this problem in which  
protecting a vertex has an associated cost, and we are free to protect  
multiple vertices per turn, up to a given cost budget (CFIRE).  
The costs are determined in function of the vertex, the current turn, and the  
state of the graph (which vertices are burning or protected).  
  
The paper shows that the properties of the cost function have a large effect  
on the complexity of the problem, as it is NP-complete for very simple  
instances (subdivided stars with two children added to each leaf).  
Additionally, their results show that CFIRE is considerably harder than FIRE,   
as FIRE is polynomial-time solvable for the instances obtained in the  
reduction above.  
They also show that the problem is tractable in so-called PathContainable  
(tree) instances, and complete graphs.  
Finally, they show that the problem is FPT parameterized by a combination of  
treewidth, budget and maximum time step.  
  
In my opinion, this variant of the problem would be interesting if there were  
some unexpected tractability results that would make it useful.   
However, since the cost functions are so general, the problem becomes  
considerably harder, and unsurprisingly NP-hard even on very simple cases.  
In other words, I think the paper could use a stronger motivation for  
introducing this variant, be it through surprising results or a strong connection   
to practice.  
The authors do present a motivation in the form of cost functions which model  
human behaviour in an epidemic, but they do not seem reasonable to me and are  
not based in any knowledge of the real world.  

***Idea for motivation: game balancing. Run lots of simulations, e.g. varying density ER graphs, for Fire and then CFire, show how much more often CFire can be solved and that can be won on more dense graphs for a "good" (read: interesting) choice of cost function and budget, so CFire becomes a more "fun" game to play (even if it is shit as an epidemic model, like Fire).***
  
As to the paper and its results, I find that they are not particularly deep,  
mostly adopting techniques of other papers to this setting.  
The writing could also be significantly improved in terms of structure,  
clarity, and correctness.  
In particular, several important cases seem to be forgotten (or at least not  
mentioned), and technically incorrect or ambiguous statements appear throughout the paper.  
Were all of the writing issues fixed, the paper might find a place at ALGOWIN,  
but as it is, I recommend rejecting the paper.  
  
  
  
# Issues with the content  
  
- The proof of Thm 2 seems to have some issues:  
 + You state that C_{i-1} and C_i have cost 1 at time n < i <= 2n, but I  
   think you mean that C_{i_1}, C_{i_2}, C_{i_3} have cost 1 at time n+2i-1  
   and n+2i for 1 <= i <= m (this is supported by the lines below)  
 + Both sides of the argument seem to be very loosely made. When given the  
   assignment, it is actually not possible to save one clause per vertex on  
   times n < t <= n+2m, because we have saved 3n = n + 3m/2 vertices up to  
   time n, and thus there are only 3m/2 more to save. Instead, the argument  
   should be made that, for every clause, all three copies can be saved.  
 + It should also be mentioned at some point that only the literal and clause  
   vertices can be saved.  
 + On the second part, it should again be argued that only these n+3m  
   vertices can be saved, and thus the total can only be achieved if for every  
   clause, all three copies are saved, as only n literal vertices can be saved.  
 + Finally, it is not true that "if the selection of n literal vertices  
   saves m clause vertices, the variable assignment is satisfying", as more  
   than one copy of the same clause can (and will) be saved.  
  
- I find Definition 3 problematic for its (implicit) dependence on a specific strategy:  
 + Particularly, the definition is for an instance, but Points 1 and 2  
   mention burning and open vertices, which depend on a strategy.  
 + You later say that "this definition is independent of strategy played" but  
   this is not stated in the definition. I assume you mean that Points 1 and  
   2 should hold for any strategy, but this needs to be stated.  
  
- Unless I misunderstand something, Theorem 4 seems to be wrong:  
 + If G is a path with 3 vertices: u -- r -- v, and costs on u and v are b-1  
   and b respectively, then the instance is PathContainable but costs are not  
   uniform, which contradicts the theorem.  
  
- Proof of Thm 10, "Since [...] this expression is clearly of length  
 polynomial in the size of the instance": I am quite sure that the EMSO formula  
 should have *constant* size (for bounded parameters), not polynomial.  
 This is supported by Bazgan et al. [JCSS 2014, Sec. 4, Point 2], when they  
 mention that the size depends on k and b.  
  
- Though a minor concern in comparison, the example of static cost function in  
 the figure introduces unnecessary technical ambiguity: what exactly is meant  
 by "costs are uniform random integers"?   
 I assume this means that n integers are generated and a function created  
 from the samples, but it could as easily be interpreted as meaning that c(v)  
 is now a random variable that we analyze in expectation.  
  
- in page 1, you state that "at time 0, we select a vertex r ∈ V for the  
 outbreak of fire, leaving all other vertices open". This is not the usual  
 definition of FF, or the one you use later, in which r is given in the  
 input.  
  
  
  
# Organization and Writing  
  
The writing of the paper should be thoroughly revised for readability. In  
particular the paper should be more structured, with different types of content  
(motivation, related work, own contributions, techniques) separated into  
logical sections; the paper should also try to be as clear as possible to the  
reader.  

*Introduced these sections.*

I recommend seeking the help of an experienced researcher to get further  
feedback.  

*Agree - I need help, don't want to ask as so embarrassed about these comments, need to try and work diligently by myself first.*
  
- In the abstract, start by presenting the firefighter problem, as it is not  
 clear that the reader knows it.  

*First pass done.*
  
- Also in the abstract, it is common to separate the results into a different  
 paragraph.  

*Also first pass done.*
  
- Please avoid using references as grammatical objects ("in [X]").  
 Instead, either tack them at an appropriate point of the sentence without  
 referring to them (e.g."the problem is known to be NP-hard [X]"), or name  
 the authors ("Y et al. prove that the problem is NP-hard [X]")  

*Will need to change this as I go through.*

- In page 1-2, the whole paragraph starting with "We first give graph  
 theoretic", as well as the formal definition of the problem (in the box)  
 should be moved to a Preliminaries section.  
 + In fact, most things in the paragraph could be omitted, since they are  
   standard graph notation.  

*Mileage may vary? Had exact opposite advice from previous review*
  
- I would like to see a much more expanded section on related work. FF and  
 related problems have a vast collection of works, including minimization and  
 maximization versions, approximation, etc.  

*Working on this.*
  
- I recommend including formal theorems in the Contributions section (Sec 1.1)  
 so the reader can immediately see a collection of the results proved in your  
 paper (and can judge, just from the Introduction, if they want to read the  
 technical content).  

*Tried to do this, not sure I have characterised all results correctly or even ordered in a coherent way, will catch on first pass after amendments.*
  
- I find it much easier to navigate a paper when counters for statements (theorems, lemma, etc) are:  
 + unified (no Theorem 1 and Lemma 1, rather each number is only assigned to a single statement)  
 + separated by section (so the first statement in Section 3 is Theorem/Lemma/... 3.1)  

*Unfortunately this is formatted as publisher required, don't think I was allowed to change.*
  
- Whenever possible, make an effort to separate the preconditions and inputs  
 from the statement of the lemma/theorem, or the definition.   
 + For example, in Definition 1, you could write:  
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

*Working on this as I go through.*
  
- Please use \emph in definitions to introduce new terms.  

*Working on this as go through.*
  
- You use the variable T in at least 3 different ways: as a tree, as an  
 interval in Def. 2, and as a time step later on. Please avoid this mixing.  
 + In Definition 2, T seems unnecessary, as you could use [0, |sigma|] directly  
 (and define it in the prelims to mean just the integers).   

 *Absolutely right should change.*
  
- In Def. 2, you could define Fraktur S as the current co-domain of the  
 functions S_{I, sigma}, and define those as going to Fraktur S. So,  
   Fraktur S = {((v1, x), (v2, x), . . . , (vn, x)) | x ∈ {burning, defended, open}  
   S_{i, sigma}: [0, |sigma] -> Fraktur S  
 You could also define Fraktur S simply as {b,d,o}^V(G), which simplifies it  
 by avoiding the numbering of vertices.   
 Regardless, a formal definition of Fraktur S is necessary.  
  
- Please define "feasible strategy" as a sigma satisfying all of the  
 constraints of CFire, so you can simplify the definitions.  
  
- The paragraph "For an instance of CFire" in page 4 would feel more natural  
 in the introduction, to show the different uses of your problem.   
 The same could be said of the discussion on how state-dependent functions  
 can model behaviours in an epidemic.  
  
- I feel like Lemma 1 and Theorem 1 are not really necessary.   
 Regarding Lemma 1, I expect that the audience of the conference will be able  
 to show that CFire is in NP.    
 For Theorem 1, it can be replaced by a sentence saying that CFire directly  
 generalizes Fire when b=1 and costs are uniform and 1.  
  
- The sentence "As k is already a variable in CFire, ..." in page 10 is not  
 necessary, it is quite clear what the \ell in P_\ell-free graphs means  
 (though you should probably clarify that it refers to *induced* paths).  
  
- Please clarify that your algorithm is FPT by *a combination of* the three  
 parameters, as it could be understood as FPT algorithms for each of them.  
 You can alternatively say that it is FPT by the sum of treewidth, budget   
 and maximum time step.  
 + You should also be more formal in Thm 10 and write "FPT parameterized by  
 tw + b + T", which clarifies the issue.  
  
- I find the summary of the paper in Section 3 unnecessary, as we are not  
 talking about a >100 page document, and the same things are said in the  
 Introduction. You can keep the open problems / conjectures part, but moving  
 it to the Introduction would also be perfectly fine.  
  
- Figures are usually set as floats on the top or bottom of the page, without  
 text wrapping around them.  
 In certain exceptional cases, they can be placed on the side of the page,  
 but I would say that they should be on the outside edge and in close  
 proximity to the relevant content.  
 In other words, you should just put both Figure 2 and 3 at the top or bottom  
 of the page (possibly even combined into a single figure!), but if you insist  
 on placing them in text (and the publisher allows it), Fig. 2 should be on  
 the right, and Fig. 3 should be within the proof of Thm 3.  
  
  
  
# Smaller issues and typos  
  
Suggestions for words to remove are marked like ~this~, for new words or changes like *this*  
Pages are indicated using the printed numbers  
  
- p. 1, Instead of "a Firefighter problem variant", it is clearer to use "A variant of the Firefighter problem".  
- p. 1, "vertices have costs to defend" -> "defending each vertex has a cost"  
- p. 1, "We express..." -> "We also show that the variant is FPT by the  
 combination of tw, budget, and maximum time step, as a consequence of  
 expressing the problem in monadic second-order logic"  
- p. 1, "discrete-time *one-player* game *on a graph* [...] ~represented by a graph~"  
- p. 1, "In each turn of a game of Fire, *a small subset of vertices can be  
 selected to become defended, after which undefended vertices catch fire if  
 they neighbor a burning vertex*"  
- p. 1, "This continues until ~fire is contained, when~ no open vertex"  
- p. 1, "At this point, *we say that the fire is \emph{contained} and* declare all..."  
- p. 1, "Naturally, the key feature..." -> "In this variant, defending a vertex has a cost which can depend on ..."  
- p. 1, "~As firefighters~"  
- p. 1, "defense budget *that* limits"  
- p. 1, "~) and the game continues as before~"  
- p. 2, "In a game of CFire" -> this later turns into b-Fire. Clarify  
- p. 2, You seem to use defender and firefighter interchangeably. Please use only one of them.  
- p. 2, Remove the sentence "Intuitively, NP-hardness of ...", or at least  
 move it before stating the NP-hardness in the previous sentence (but remove  
 "Intuitively" nonetheless)  
- p. 2, "b-Fire is NP-complete *for every b, even for instances with maximum degree b+2*"  
- p. 2, "*Our variant generalizes b-Fire by introducing* temporality to the problem"  
- p. 2, State whether CFire generalizes TFire.  
- p. 2, "weights of the saved vertices *--* see Duffy...": use en- or em-  
 dashes for separating clauses.  
- p. 2, "Work has been done": passive voice is generally discouraged as  
 awkward and hard to read.  
- p. 3, break paragraph before "We denote by (*)"  
- p. 4, "strategy \sigma ~(as in Definition 1)~, such that"  
- p. 4, "as an oracle because *storing Fraktur S extensively requires exponential space.*"  
- p. 4, "In practice, we keep track... to avoid this calculation.": which calculation?  
 If you mean explicitly computing Fraktur S, I don't think anyone would assume that.  
- p. 4, "This definition requires budgets and costs to be integers": I  
 disagree, it would work just as well with rationals.  
- p. 4, "Example 2 ~(Distance from root)~. *The cost function c(v) = dist(r,v) is a static function."  
- p. 4, "This function maps...": this sentence is quite unnecessary, as it does not add any information.  
- p. 5, Consider removing the "Example X" statements and simply referring to the Figure for comments.  
- p. 5, "which may be computationally expensive": why would it?  
- p. 6, give a name to the graphs in Theorems 2 and 3 so you are not always repeating the description.  
 It could be e.g. "forked-feet spiders" or anything else you like.  
- p. 6, what are "*explicitly* temporal cost functions"?  
- p. 6, "in the *theorem* statement": capital letter only when there is a number  
- p. 7, degree-one vertices are usually called leaves, but in the construction  
 you can also say the "first vertex of the path"  
- p. 7, "Fire is decidable *in polynomial time*"  
- p. 7, "Observe that there is no need to place more than one defence on a  
 tree if we defend beside fire": I do not understand what this means, but it  
 does not seem necessary  
  
  
  
----------------------- REVIEW 3 ---------------------  
SUBMISSION: 18  
TITLE: Firefighting with defence costs  
AUTHORS: Ethan Hunter and Jessica Enright  
  
----------- Overall evaluation -----------  
SCORE: 0 (borderline paper)  
----- TEXT:  
The authors study a variant of the Firefighter problem. In simple terms, the Firefighter setting consists of a graph, where at some arbitrary time, a set of the vertices start ``burning''. In every round, the fire spreads from a burning vertex to adjacent ``safe'' vertices. This process continues until every vertex is burned. The ``Firefighters'' are able to defend vertices, such that the fire is not spread to them. In practice, this setting models a spreading process among vertices, where we can protect some vertices to stop the infection. The question asked is, which vertices should we defend in order to maximize the vertices that get saved. The novelty of this paper is that it considers different functions that assign costs to defend the vertices. The functions that they consider depend on any combination of the following factors: the vertex considered, the state of the graph, the round of the process.  
  
The main results are:  
-The problem is NP-hard for cost functions that depend on time even on very restricted rooted tree graphs.  
-The problem is polynomially time solvable on complete graphs, P_l free graphs and fpt by treewidth, budget and maximun number of time-steps  
  
Positives:  
-Interesting problem  
  
Negatives:  
-Not well written  
  
Opinion of the reviewer:  
-I think that the problem studied by the authors is quite interesting and the results are a bit involved. I like the problem setting and it is worthwhile to study what happens when there are different functions costs that capture different scenarios. I think that the complexity of the results is not very high but it is also not very straightforward. I had already reviewed the paper for another conference and my main complaint was that the paper was not well written. Since then, the authors have implemented many changes that makes the paper more rigorous and easier to read but there are still a lot of things that are ill-defined and are left unclear to the reader which makes the paper difficult to read. If the paper was well written, I would lean towards accept but in its current form, I think it is at best, a borderline paper.


-----
 
**Consider:**


**Source:** 


**Reference:** 
