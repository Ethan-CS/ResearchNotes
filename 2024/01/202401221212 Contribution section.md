Tags :
Zettel :  20240122-1212
Status : #triage 

-----

# Contribution section

**Previous note:** [[202401171036 With-reserve 'equivalence']]

-----

### Questions & thoughts:

After giving preliminaries and background information in Section 2, we define our variant of \Fire that takes a function specifying costs to defend each vertex of the input graph, depending on time and the state of the problem in Section 3. We explore different types of cost functions before giving a proof in Section 3.2 that this problem is NP-complete (with a hardness reduction from Fire) 2. We provide a nuanced picture of the tractability of cost function firefighting by identifying graph classes where only \Fire is tractable, where both \Fire and \Cfire is tractable, where \CFire is tractable only under certain inputs and where both \Fire and \CFire are tractable but \TFire is not. In particular, we show that both the original and cost function problems are tractable on $P_k$-free graphs but the cost function problem remains hard on trees of bounded degree without extra restrictions on the graph and cost function. We define and explore the benefits of these extra restrictions and explain how they effectively re-couple the degree and cost to defend analogously to the original problem. We also express our variant of Fire in a fragment of second-order logic to show that it is fixed-parameter tractable with respect to treewidth of the input graph, the budget and the minimum number of vertices saved.


-----
 
**Consider:**


**Source:** 


**Reference:** 
