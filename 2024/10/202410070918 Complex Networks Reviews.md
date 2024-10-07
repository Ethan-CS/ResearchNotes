Tags :
Zettel :  20241007-0918
Status : #triage 

-----

# Complex Networks Reviews

**Previous note:** [[202410021806 DP for CFire on graphs of bounded degree]]

-----

### Questions & thoughts:

Reviews are only in the conference system, I'll link them here:

- **Detailed Evaluation (Contribution, Pros/Cons, Errors)**
    - The paper introduces a novel variant of the Firefighter problem, termed the Cost Function Firefighter (CFire), in which defending nodes involves a dynamic cost that fluctuates over time or in response to the proximity of fire. This work delves into the computational complexity of the problem, demonstrating that it remains NP-hard even in scenarios where the original Firefighter problem is solvable. The authors propose heuristics that prioritize node degree, proximity to fire, and defense costs, and empirically test these strategies on various random graph classes. The study reveals that the performance of these heuristics is strongly dependent on both the graph structure and the chosen cost function, providing valuable insights into practical methods for network defense against contagion.  
    - I find the research question posed in this paper intriguing, and the methodology appears rigorous, producing nontrivial results. Below are a few suggestions that may further enhance the paper:  
        1. The random graphs used in the simulations are all small-world networks, which introduces a certain bias to the tests. It might be beneficial to explore “wider” networks with longer average path lengths, as these could offer a fresh perspective. Even within random graph models, node-duplication models are known to generate more extended structures. Including this, and potentially incorporating real-world networks, would be worth considering.  
        2. Among the empirical heuristics, particular emphasis is placed on the distance from the fire. This raises the question of whether existing research on the distribution of shortest paths in networks could contribute to more robust analytical results for these approaches.  
        Overall, I recommend the paper for acceptance as an oral presentation.  
        

## **Reviewer #2**

- **Detailed Evaluation (Contribution, Pros/Cons, Errors)**
    - The paper considers an interesting extension of the firefighter game which is a well studied relevant problem. The authors give formal proof for the hardness of the problem and using some heuristics, some experimental results are also presented. The paper is well written, even though it has some limitations.  
        1. Concerning heuristics they are considering only the appropriate modifications of methods of a single paper. It can be fine, but the choice should be reliable justified. In the state of the art no other paper is mentioned concerning heuristics with firefighter - this should be extended and the choice should be justified.  
        2. Theorem 4 is not proved, just very shortly highlighted. There is appropriate space for this, so it should be added.  
        3. In the experimental part testing is made with graphs of 50 nodes. It is quite limited and should be explained the reason of this choice.

## **Reviewer #3**


- **Detailed Evaluation (Contribution, Pros/Cons, Errors)**
    - Tis work addresses a generalization of a nice discrete-time game, called FIRE: given a graph and a root vertex indicating the initially burning node, the player seeks at saving a maximum number of nodes by defending a node at its turn, knowing that some nodes may catch fire at every other turn (in general nodes that have a burning neighbor).  
          
        The proposed generalization, called CFIRE, includes a time-depending cost-function, which assigns costs to each node in order to be defended. More formally, the input comes with a budget (integer) and a cost-function that associates a natural number to each node given a game state (i.e. burning and defended nodes) and time step. The defender can only defend nodes for which the sum of the costs do not exceed the budget. This generalization adds some temporality to the problem, and differs from Budget Firefighter that was previously considered with the budget addition only. Moreover, the only consideration of temporality known to the authors came from a study of FIRE where the input graph was a temporal one.  
          
        From the theoretical viewpoint, the authors prove that CFIRE is NP-Hard on particular instances, called sea fans. Interestingly, they prove in contrast that FIRE is polynomial-time solvable on such graphs. The authors moreover provide an algorithm for graphs that do not contain paths of length l as subgraphs by adapting a known algorithm. Such an algorithm runs in time O((n+m)^{bl-2}) and is thus an XP algorithm parameterized by both b and l (and hence the pathwidth of the input graph).  
          
        Regarding experiments, the authors consider several strategies on arguably small graphs (50 nodes), that is defending high-degree nodes first, lowest costs or smallest distance to a burning node. Variants of the first and last strategies are considered by breaking ties using the cost-based one. To generate random instances it is also needed to compute cost functions, which is done by considering uniform random costs varying between 1 and 5, threat-based costs (distance to closest burning node), also with a stochastic factor. The budget is set to 5 in all experiments, that are ran 1000 times on each trial, regenerating both the graph and the costs.  
          
        Two models are considered, random regular graphs (with degree 6) and Barabási–Albert graphs with six edges added when each node is added. While the obtained results are not really surprising (the different heuristics perform better on threat-based costs functions) they do give some insights for future work.  
          
        While the hardness, tractability and experimental results presented in this paper are not surprising they provide nice perspectives for future research on a newly introduced problem. I hence recommend the paper for publication.  
          
        Below are some minor comments for the authors:  
          
        - Theorem 1: ''provided that (the) the root``  
        - Theorem 3: is the ''central node`` the root?  
        - Proof of Theorem 3:  
        + ''Observe that the input formula`` instead of satisfying assignment?  
        + the reference for the NP-Completeness of 2N2P-SAT does not seem to be the right one, I did not find any mention of this problem in [2]. I think the right one is Higher-order matching in the linear lambda calculus in the absence of constants is NP-complete by R. Yoshinaka? (But I may have misread something in the former paper)  
        + should k < k + 3m be k < n + 3m?  
        + last sentence: ''unsuccessful strategy for CFIRE``? (instead of 2N2P-SAT)  
        - Figure 1: you could maybe start from a small formula to derive the sea fan of the reduction?  
        - First sentence of 4.1: ''Here`` instead of ''He``?  
        - First sentence of 4.2: ''*we* implemented heuristics``?

## **Reviewer #4**

- **Detailed Evaluation (Contribution, Pros/Cons, Errors)**
    - The paper is original and quite interesting in its content. I believe this is a reasonably strong submission for the scope of the conference.  
          
        I have no edits to recommend.

-----


## Actions from Reviews

 - [ ] Use of small, small-world graphs
	 - [ ] Justify - why so small (motivation for further experiments)?
	 - [ ] Justify - why small-world (easy start)?
	 - [ ] Introduces certain bias
	 - [ ] Would like to explore 'wider' networks with longer average path length, e.g. node-duplication models
	 - [ ] Real-world networks
 - On empirical heuristics
	 - [ ] We emphasise distance from fire - could existing research on distribution of shortest paths in networks contribute to analytical results for these approaches? Something to add to future work?
	 - [ ] Only consider modifications of heuristics from one existing paper - explain why
	 - [ ] Explain existing heuristics for FF, including mentioning state-of-the-art
 - [ ] Theorem 4, not proved, but there is space to do this
 - Typos etc, from reviewer 3:
	- [ ] Theorem 1: "provided that (the) the root"
	-  [ ] Theorem 3: is the "central node" the root?  
	- [ ] Proof of Theorem 3:  
        + [ ] "Observe that the input formula" instead of satisfying assignment?  
        + [ ] the reference for the NP-Completeness of 2N2P-SAT does not seem to be the right one, I did not find any mention of this problem in ref. 2. I think the right one is Higher-order matching in the linear lambda calculus in the absence of constants is NP-complete by R. Yoshinaka? (But I may have misread something in the former paper)  
        + [ ] should k < k + 3m be k < n + 3m?  
        + [ ] last sentence: "unsuccessful strategy for CFIRE"? (instead of 2N2P-SAT)  
        - [ ] Figure 1: you could maybe start from a small formula to derive the sea fan of the reduction?  
	- [ ] First sentence of 4.1: "Here" instead of "He"?  
	- [ ] First sentence of 4.2: ''*we* implemented heuristics"?