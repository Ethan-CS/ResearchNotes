Tags :
Zettel :  20230829-1341
Status : #triage 

-----

# Addressing Manuscript Reviews

**Previous note:** [202308231511 Manuscript Feedback](202308231511%20Manuscript%20Feedback.md)

-----

### Questions & thoughts:

1. **The authors must make it clear that these systems are only exact on either tree networks with no loops or on graphs with loops if the closures leave the loops intact. This needs to become obvious early on.** 
*Section 2.2.3 Exact Moment closures: "Note that closures in our context are exact for graphs containing cycles only if cycles in the graph are preserved under closures \cite{kiss_2014} - we ensure this is the case by first identifying cut vertices in graphs, then introducing closures for terms referencing these vertices case-by-case, thereby preserving cycle structures."*
2. **Pages two and three are very dry with literally endless definitions of well-known concepts. Can these be presented differently, maybe in a table or something? It just makes the paper very difficult to read with no linking text or motivation between the 11 definitions.**  
We are grateful for this suggestion. We have added a sentence signposting that these are standard definitions, which can be skipped by those familiar with them, and they have been condensed into paragraphs rather than standalone definitions, hopefully ensuring reading these is a more comfortable experience.
1. **I think some of the original papers say that the system needs to start in a pure state for the closures to make sense. Pure means that the system is one of its m^n configurations with probability one at time t=0. So, to me proposition 3.1 is not surprising.**
We agree that the proposition is not entirely surprising, however we believe it is an important addition because... (spend max 30 mins looking at previous papers, see if we can understand this pure state; add some text saying not very surprising; loop in Alice, see if she knows why this tracks) (not surprising, continue to include for completeness as a concrete example of not being generalisable, added text saying as much)
1. **More importantly to my knowledge and memory, when one writes down equations, generate them, the nodes in the cut set when a closure is needed will never need to be in any other state than the S state. This is the beauty of the procedure, that these nodes are never needed to be in I or R states when a triple or bigger structure needs to be closed. If one wants to write down the full system with all possible configurations then yes, nodes in the cut set can be in S and I or R or some other state depending on the dynamics. However, in a bottom-up approach, writing equations for singles will involve pairs and pairs will involve triples but it turns out that cut vertices in triples or bigger structures will always be in the S state. One should say that for writing down equations a bottom-up approach is used as the top-down is too complex due to the high number of equations. Oh I see, this is said in Observation 3.7.** 
This is an important point - we have moved the mentioned observation earlier (just before Theorem 3.5) and added a sentence (TODO) about how this could be tackled using a top-down approach but this leads to vastly larger numbers of equations.
1. **Is ER a good network to test this approach on? ER will have loops and the exact equations will not be exact, or are the cut-sets identified and the closures are done around them?** 
Yes, they are for the reason described - the procedure preserves cycle structures by first identifying cut-vertices _then_ closing where possible, thereby never compromising the structure of a cycle. Intentionally, we can not always use closures in hthese graphs. (This has been tested by generating and solving full and closed systems for several sets of initial conditions and comparing the results.)
1. **In figure 11, I would lot the y=x diagonal to show that in most cases the points lie below it.** 
(1) no such figure but (2) assuming I know which one this is, doing this looks very strange because of the much different scales in the x and y axes, hence the colours to indicate which method was faster.
7. **I was surprised to see no pseudocode or code to explain how the authors come up with the computational method/framework. I would add a whole section explaining this, what language and how the code works in general terms. At the end this is the main contribution of the paper.**  
(Working on this)

Reviewer 2

1. Strictly speaking, equation (5) only gives na upper bound on the number of equations and an extra argumente is needed in order to explain that the exponential upper bound is achieved by a specific configuration. Otherwise, it is misleading to state in the Introduction "such systems scale exponentially" and it would be better to write "such systems scale at most exponentially".
2. In the remaining part of the Introduction it would be good to further emphasize that the results of 3.2 and 3.3 assume specific forms of the graphs fow which moment closure conditions hold and that such whether proven in the reference [2].  
(In signposting for this section, make even more clear that these results only apply on these restricted classes of graphs and only because these allow us to exploit closures effectively)
1. There is something confusing in definition 2.5 as both H and G[H] are used to denote the subgraph.  
2. The notation in Propositions 3.1 and Theorem 3.5 should be better explained. Right now, one needs to go through notation 2.1 and definition 2.14. I suggest giving na exemple after definition 2.14 just as there is an example after notation 2.1.  
3. In section 4 the authors consider random graphs. For certain simple models of disease propagation on some of these there are some extra conserved quantities which may be used to further reduce the system of equations. See Mark Newmann's book "Networks: An Introduction" from Oxford University Press, 2018.  There is also a more recent version of these conserved quantities developed to some more refined models in the article "New approaches to epidemic modelling on networks." Published in Scientific Reports earlier this year 2023.  
(add into discussion, unless there's something really obvious that we should add in and we need to ask for more time from editor.)
  

-----
 
**Consider:**


**Source:** 


**Reference:** 
