Tags :
Zettel :  20240207-1349
Status : #triage 

-----

# Spreading Vaccination - related work

**Previous note:** [[202401301909 Reduction feedback from Jess]]

-----

### Questions & thoughts:

Jess and I originally thought there was nothing on the infectious vaccination problem. I've found two papers[^1],[^2] that mention the 'spreading' firefighter problem in the last few days. I summarise the problems and results as follows.

Traditional fire: rooted graph $(G, r)$, fire starts at $r$ and at each subsequent time-step: we defend up to $b$ vertices, then the fire spreads to any undefended and unburned vertices. This continues until fire can no longer spread. Spreading model: defence (referred to by both sources as vaccination) spreads in the same way as fire (to all undefended and unburned neighbours). They[^1] do not make it clear which spreads first, fire or vaccination. The authors[^1] consider both a minimum-budget-used objective and a maximum-number-saved objective at different times for the vanilla and spreading problems.

The spreading problem is more tractable than the vanilla problem (section 3).[^1]

|  | Spreading | Non-spreading |
| ---- | ---- | ---- |
| Max-save | $(1-1/e)$ approx. | $n^{(1-\epsilon)}$-hard for $\epsilon>0$ |
| Min-budget | $\ln n$ approx and $(1-o(1))\ln n$-hard | General: $2\sqrt{n}$-approx, directed $\ell$-layered graph: $H(\ell)$-approx |
  
Lemma 3.1: I think this is basically the same as result in most recent paper (length of time the process can run is bou)





-----
 
**Consider:**


**Source:** 
[1]: Anshelevich, E., Chakrabarty, D., Hate, A., Swamy, C. (2009). Approximation Algorithms for the Firefighter Problem: Cuts over Time and Submodularity. In: Dong, Y., Du, DZ., Ibarra, O. (eds) Algorithms and Computation. ISAAC 2009. Lecture Notes in Computer Science, vol 5878. Springer, Berlin, Heidelberg. https://doi.org/10.1007/978-3-642-10631-6_98

[2]: P Floderus, A Lingas, M Persson, *Towards more efficient infection and fire fighting,* Proceedings of the Seventeenth Computing: The Australasian Theory Symposium (CATS 2011), Perth, Australia



**Reference:** 
