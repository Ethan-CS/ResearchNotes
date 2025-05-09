Tags :
Zettel :  20230906-1645
Status : #triage 

-----

# State-of-Play of Revisions

**Previous note:** [202309040814 Condensing Definitions](202309040814%20Condensing%20Definitions.md)

-----

### Questions & thoughts:

##### Reviewer #1

 - [x] The authors must make it clear that these systems are only exact on either tree networks with no loops or on graphs with loops if the closures leave the loops intact. This needs to become obvious early on. 
*Text added explaining this: "Note that closures in our context are exact for graphs containing cycles only if cycles in the graph are preserved under closures \cite{kiss_2014} - we ensure this is the case by first identifying cut vertices in graphs, then introducing closures for terms referencing these vertices case-by-case, meaning cycle structures are not broken.* pp. 6-7 (give line number when re-generated in editorial manager)"".
 - [x] Pages two and three are very dry with literally endless definitions of well-known concepts. Can these be presented differently, maybe in a table or something? It just makes the paper very difficult to read with no linking text or motivation between the 11 definitions.  
*These definitions have been collated into a paragraph and a sentence has been added indicating that the definitions are very standard, so can be skipped by those familiar with graph theory.*
 - [ ] I think some of the original papers say that the system needs to start in a pure state for the closures to make sense. Pure means that the system is one of its m^n configurations with probability one at time t=0. So, to me proposition 3.1 is not surprising.  
 - [x] More importantly to my knowledge and memory, when one writes down equations, generate them, the nodes in the cut set when a closure is needed will never need to be in any other state than the S state. This is the beauty of the procedure, that these nodes are never needed to be in I or R states when a triple or bigger structure needs to be closed. If one wants to write down the full system with all possible configurations then yes, nodes in the cut set can be in S and I or R or some other state depending on the dynamics. However, in a bottom-up approach, writing equations for singles will involve pairs and pairs will involve triples but it turns out that cut vertices in triples or bigger structures will always be in the S state. One should say that for writing down equations a bottom-up approach is used as the top-down is too complex due to the high number of equations. Oh I see, this is said in Observation 3.7. 
*Just before exact moment closures section: "We refer to this method of equation generation as a bottom-up approach. We could instead write down equations for all possible terms in a top-down approach, which would lead to a far greater number of equations." Before Theorem 3.5: "In an $SIR$ model, it is shown in \cite{kiss_2014} that cut-vertices only ever appear in moments in the susceptible state, so Theorem \ref{thm:kiss-main} is a corollary of the following theorem when the size of the cutset is one (and the following theorem is not entirely surprising). The vertices of cutsets of size two or more are not guaranteed to all be in outlet states, unlike single vertex cutsets (cut-vertices) which only appear in outlet states."*
 - [x] Is ER a good network to test this approach on? ER will have loops and the exact equations will not be exact, or are the cut-sets identified and the closures are done around them?
*Hopefully addressed by the additional explanation for the first point.*
 - [x] In figure 11, I would lot the y=x diagonal to show that in most cases the points lie below it.
*We agree that this seems a helpful addition, but we tried to plot this diagonal and because of the scale of the axes it served only to obscure points. To make it clear just how much faster one approach is over the other, we have added this text in the caption: "Note that the difference in axes scales is considerable, so the $y=x$ diagonal has not been plotted and it is clear that simulation was always faster than generating and solving equations."*
 - [ ] I was surprised to see no pseudocode or code to explain how the authors come up with the computational method/framework. I would add a whole section explaining this, what language and how the code works in general terms. At the end this is the main contribution of the paper. 
  
  
#### Reviewer #2
 - [ ] Strictly speaking, equation (5) only gives na upper bound on the number of equations and an extra argumente is needed in order to explain that the exponential upper bound is achieved by a specific configuration. Otherwise, it is misleading to state in the Introduction "such systems scale exponentially" and it would be better to write "such systems scale at most exponentially".  
 - [ ] In the remaining part of the Introduction it would be good to further emphasize that the results of 3.2 and 3.3 assume specific forms of the graphs fow which moment closure conditions hold and that such whether proven in the reference [2].  
 - [ ] There is something confusing in definition 2.5 as both H and G[H] are used to denote the subgraph.  
 - [ ] The notation in Propositions 3.1 and Theorem 3.5 should be better explained. Right now, one needs to go through notation 2.1 and definition 2.14. I suggest giving na exemple after definition 2.14 just as there is an example after notation 2.1.  
 - [ ] In section 4 the authors consider random graphs. For certain simple models of disease propagation on some of these there are some extra conserved quantities which may be used to further reduce the system of equations. See Mark Newmann's book "Networks: An Introduction" from Oxford University Press, 2018. There is also a more recent version of these conserved quantities developed to some more refined models in the article "New approaches to epidemic modelling on networks." Published in Scientific Reports earlier this year 2023.  



-----
 
**Consider:**


**Source:** 


**Reference:** 
