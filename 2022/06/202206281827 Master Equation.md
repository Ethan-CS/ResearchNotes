Tags : #Equation #Dynamical #Kolmogorov
Zettel :  20220628-1827
Status : #complete 

-----

# Master Equation

**Previous note:** [202206281759 Num Subpaths Result](202206281759%20Num%20Subpaths%20Result.md)

-----

## Full System Master Equation

Info about master equations used for deriving equations for system/subsystem states.

Master equation for **full system states**
- Consider the state $\Gamma^\alpha$ of an arbitrary system $\Gamma$
- $\Gamma^\alpha=1$ if $\Gamma$ is in the state $\Gamma^\alpha$, 0 otherwise.
- The probability (numerically equivalently, expected value) of $\Gamma$ being in state $\Gamma^\alpha$ is $$\dot{\langle\Gamma^\alpha\rangle} = \sum_\beta\sigma^{\alpha\beta}\langle \Gamma ^\beta \rangle - \sum_\beta\sigma^{\beta\alpha}\langle\Gamma^\alpha\rangle$$
-  Where $\sigma^{\alpha\beta}$ represents the rate of transition from $\Gamma^\beta$ to $\Gamma^\alpha$

# Subsystem Master Equation
- Suppose there are well-defined subsystems in $\Gamma$, denoted $\psi_i$ where $i$ distinguishes one subsystem from another.
- The probability (numerically equivalently, expected value) of $\psi_i$ being in state $\psi_i^a$ is  $$\dot{\langle\psi^a_i\rangle} = \sum_b\omega^{ab}_i\langle\psi^b_i\rangle - \sum_b\omega_i^{ba}\langle\psi_i^a\rangle $$
- Where $\omega_i^{ab}$ represents the rate of transition from state $\omega_i^b$ to $\omega_i^a$ for the subsystem $\psi_i$.
- Each of these master equations can be derived from the other, as shown by Sharkey



-----
 


**Source:** Kieran J. Sharkey, _Deterministic epidemic models on contact networks: Correlations and unbiological terms,_ Theoretical Population Biology, Volume 79, Issue 4, 2011, pp. 115-129
