Tags :
Zettel :  20230823-1511
Status : #triage 

-----

# Manuscript Feedback

**Previous note:** [202307271330 Firefighter Motivation Rewrite](202307271330%20Firefighter%20Motivation%20Rewrite.md)

-----

### Questions & thoughts:
  
Referees have evaluated your paper mentioned above. Comments are below. On the basis of these comments, the member of the Editorial Board handling your paper has decided that a minor revision is needed before your paper can be accepted. I would appreciate it if you could revise your paper within one month of this email.  
  
I look forward to receiving the revised version of your paper. You should explain how and where the reviewers' comments have been addressed by your changes to the text (overview of changes). Should you disagree with some of these comments, please explain why.  
  
To upload the source file (LaTeX, or Word) of the revised paper and the overview of changes, please log-in to the system at [https://www.editorialmanager.com/tcs/](https://www.editorialmanager.com/tcs/) with  
username.
  
If you need to retrieve password details, please go to [https://www.editorialmanager.com/tcs/admin/Default.aspx](https://www.editorialmanager.com/tcs/admin/Default.aspx)  
selecting the 'Author' button.   
  
When submitting your revised paper, we ask that you include the following items:  
  
Response to Reviewers (mandatory)  
  
This should be a separate file labeled "Response to Reviewers" that carefully addresses, point-by-point, the issues raised in the comments appended below. You should also include a suitable rebuttal to any specific request for change that you have not made. Mention the page, paragraph, and line number of any revisions that are made.  
  
Manuscript and Figure Source Files (mandatory)  
  
We cannot accommodate PDF manuscript files for production purposes. We also ask that when submitting your revision you follow the journal formatting guidelines. Figures and tables may be embedded within the source file for the submission as long as they are of sufficient resolution for Production. For any figure that cannot be embedded within the source file (such as *.PSD Photoshop files), the original figure needs to be uploaded separately. Refer to the Guide for Authors for additional information.  
[http://www.elsevier.com/journals/theoretical-computer-science/0304-3975/guide-for-authors](http://www.elsevier.com/journals/theoretical-computer-science/0304-3975/guide-for-authors)  
  
Highlights (Optional)  
  
Highlights consist of a short collection of bullet points that convey the core findings of the article and should be submitted in a separate file in the online submission system. Please use 'Highlights' in the file name and include 3 to 5 bullet points (maximum 85 characters, including spaces, per bullet point). See the following website for more information  
[http://www.elsevier.com/highlights](http://www.elsevier.com/highlights)   
  
Please note that this journal offers a new, free service called AudioSlides: brief, webcast-style presentations that are shown next to published articles on ScienceDirect (see also [http://www.elsevier.com/audioslides](http://www.elsevier.com/audioslides)). If your paper is accepted for publication, you will automatically receive an invitation to create an AudioSlides presentation.  
  
Theoretical Computer Science features the Interactive Plot Viewer, see: [http://www.elsevier.com/interactiveplots](http://www.elsevier.com/interactiveplots). Interactive Plots provide easy access to the data behind plots. To include one with your article, please prepare a .csv file with your plot data and test it online at [http://authortools.elsevier.com/interactiveplots/verification](http://authortools.elsevier.com/interactiveplots/verification) before submission as supplementary material.  
  
Note: While submitting the revised manuscript, please double check the author names provided in the submission so that authorship related changes are made in the revision stage. If your manuscript is accepted, any authorship change will involve approval from co-authors and respective editor handling the submission and this may cause a significant delay in publishing your manuscript.  
  
PLEASE NOTE: Theoretical Computer Science would like to enrich online articles by displaying interactive figures that help the reader to visualize and explore your research results. For this purpose, we would like to invite you to upload figures in the MATLAB .FIG file format as supplementary material to our online submission system. Elsevier will generate interactive figures from these files and include them with the online article on SciVerse ScienceDirect. If you wish, you can submit .FIG files along with your revised submission.  
  
Include interactive data visualizations in your publication and let your readers interact and engage more closely with your research. Follow the instructions here: [https://www.elsevier.com/authors/author-services/data-visualization](https://www.elsevier.com/authors/author-services/data-visualization) to find out about available data visualization options and how to include them with your article.  
  
Research Elements (optional)  
This journal encourages you to share research objects - including your raw data, methods, protocols, software, hardware and more – which support your original research article in a Research Elements journal. Research Elements are open access, multidisciplinary, peer-reviewed journals which make the objects associated with your research more discoverable, trustworthy and promote replicability and reproducibility. As open access journals, there may be an Article Publishing Charge if your paper is accepted for publication. Find out more about the Research Elements journals at [https://www.elsevier.com/authors/tools-and-resources/research-elements-journals?dgcid=ec_em_research_elements_email](https://www.elsevier.com/authors/tools-and-resources/research-elements-journals?dgcid=ec_em_research_elements_email).  
  
  
#### Comments:  
  
Editor: The two reviewers have identified a number of concerns. Please respond to their comments and resubmit an improved version of the manuscript for a new round of reviewing. With the updated manuscript, please upload a point-by-point response to the comments of the reviewers. Also, indicate the new text in the manuscript using a different text color.  
  
##### Reviewer #1

The authors complement existing theoretical work which showed the possibility of writing down exact equations for certain type of epidemics on certain types of finite graphs. The number of equations is high, and the previous theoretical work did not give an automated way to generate and solve these equations except in some idealised cases. The authors suggest an automated way, in terms of code, that take a compartmental model and a network and then outputs and solves the resulting equations. They also provide some bounds on the number of equations depending on the number of compartments/states in the epidemic model and the size and properties of the network. Hence, the paper fills in an important gap in the literature and I am happy to recommend it for publication subject to some suggestions for revision.  
  
Comments/suggestions/questions:  
  
1. The authors must make it clear that these systems are only exact on either tree networks with no loops or on graphs with loops if the closures leave the loops intact. This needs to become obvious early on. 
Relates to (5), loops are intact as cut-vertices are identified at start of procedure and then replaced as terms would be added referencing cut-vertices.
  
2. Pages two and three are very dry with literally endless definitions of well-known concepts. Can these be presented differently, maybe in a table or something? It just makes the paper very difficult to read with no linking text or motivation between the 11 definitions.  
Not sure definitions are 'literally endless' but agree there is little motivation - look into ways to represent/condense lots of definitions - perhaps not all essential?
  
3. I think some of the original papers say that the system needs to start in a pure state for the closures to make sense. Pure means that the system is one of its m^n configurations with probability one at time t=0. So, to me proposition 3.1 is not surprising.  
Not sure I understand this.
  
4. More importantly to my knowledge and memory, when one writes down equations, generate them, the nodes in the cut set when a closure is needed will never need to be in any other state than the S state. This is the beauty of the procedure, that these nodes are never needed to be in I or R states when a triple or bigger structure needs to be closed. If one wants to write down the full system with all possible configurations then yes, nodes in the cut set can be in S and I or R or some other state depending on the dynamics. However, in a bottom-up approach, writing equations for singles will involve pairs and pairs will involve triples but it turns out that cut vertices in triples or bigger structures will always be in the S state. One should say that for writing down equations a bottom-up approach is used as the top-down is too complex due to the high number of equations. Oh I see, this is said in Observation 3.7. 
They changed their mind by the last sentence, I had addressed this in an observation?
  
5. Is ER a good network to test this approach on? ER will have loops and the exact equations will not be exact, or are the cut-sets identified and the closures are done around them?  
  
6. In figure 11, I would lot the y=x diagonal to show that in most cases the points lie below it.  
  
7. I was surprised to see no pseudocode or code to explain how the authors come up with the computational method/framework. I would add a whole section explaining this, what language and how the code works in general terms. At the end this is the main contribution of the paper.  

Our implementation first identifies the cut vertices in the graph using a depth-first search. We first obtain equations for single vertices
  
  
Reviewer #2: Review of "Feasibility Assessments of a Dynamical Approach to Compartmental Modelling on Graphs: Scaling Limits and Performance Analysis" submitted to Theoretical Computer Science  
  
I believe this article is interesting, valuable and deserves publication. I could not find any mistake and so believe the results to be correct.  
  
I have some comments that may be of use to the authors before submitting the revised final version:  
1. Strictly speaking, equation (5) only gives na upper bound on the number of equations and an extra argumente is needed in order to explain that the exponential upper bound is achieved by a specific configuration. Otherwise, it is misleading to state in the Introduction "such systems scale exponentially" and it would be better to write "such systems scale at most exponentially".  
2. In the remaining part of the Introduction it would be good to further emphasize that the results of 3.2 and 3.3 assume specific forms of the graphs fow which moment closure conditions hold and that such whether proven in the reference [2].  
3. There is something confusing in definition 2.5 as both H and G[H] are used to denote the subgraph.  
4. The notation in Propositions 3.1 and Theorem 3.5 should be better explained. Right now, one needs to go through notation 2.1 and definition 2.14. I suggest giving na exemple after definition 2.14 just as there is an example after notation 2.1.  
5. In section 4 the authors consider random graphs. For certain simple models of disease propagation on some of these there are some extra conserved quantities which may be used to further reduce the system of equations. See Mark Newmann's book "Networks: An Introduction" from Oxford University Press, 2018.  
There is also a more recent version of these conserved quantities developed to some more refined models in the article "New approaches to epidemic modelling on networks." Published in Scientific Reports earlier this year 2023.  

-----
 
**Consider:**


**Source:** 


**Reference:** 
