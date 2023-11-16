Tags : #PathContainable #Firefighter #CFire #pseudocode
Zettel :  20231116-0940
Status : #triage 

-----

# Pseudocode for Specific PathContainable Verification

**Previous note:** [[202311061609 Instant Insanity]]

-----

### Questions & thoughts:

I've taken the following out of the overleaf doc. as the logic does not work - this only works for a specific instance of CFire, given we know where the fire has been, not for a general graph. I'm keeping a note of it for later reference.


```tex
\begin{algorithm}\caption{Verify that defence under a cost function on a graph is at least as cheap beside fire as anywhere else.}\label{alg:cheapest-beside-fire}
\begin{algorithmic}[1]
    \Function{DefenceCheapestBesideFire}{graph $G=(V, E)$, end state $S_t$, $c:V\rightarrow\mathbb{N}$}
        \For{each vertex $v$ in $V$} \Comment{$O(n)$}
            \If{$v$ is burning}
            \State $t\gets$ earliest time $v$ is burning
                \For{each vertex $w$ in $N(v)$} \Comment{$O(n)$}
                    \If{$w$ is undefended \textbf{and} unburned at time $t$}
                        \For{each vertex $u$ in $V$} \Comment{$O(n)$}
                            \If{$u$ is undefended \textbf{and} unburned at time $t$}
                                \State \texttt{neighbour\_burning} $\gets$ \texttt{False}
                                \For{each vertex $x$ in $N(u)$} \Comment{$O(n)$}
                                    \If{$x$ is burning at time $t$}
                                        \State \texttt{neighbour\_burning} $\gets$ \texttt{True}
                                    \EndIf
                                \EndFor
                                \If{(\textbf{not} \texttt{neighbour\_burning}) \textbf{and} $c(u)>c(w)$}
                                    \State\Return\texttt{False}
                                \EndIf
                            \EndIf
                        \EndFor
                    \EndIf
                \EndFor
            \EndIf
        \EndFor
        \State\Return\texttt{True}
        \EndFunction
\end{algorithmic}
\end{algorithm}
```
As indicated in the comments, this is verifiable in $O(n^4)$ time.

```tex
    Part \ref{enum:path-children} of the \nice property can be verified using Algorithm \ref{alg:children-verify}.
    \begin{algorithm}\caption{Verify that we can always defend at least all-but-one children of burning vertices.}\label{alg:children-verify}
        \begin{algorithmic}[1]
        \Function{CanDefendAllButOneChildren}{graph $G=(V, E)$, states $S$, $c:V\rightarrow\mathbb{N}$, $b\in\mathbb{N}$}
            \For{each vertex $v$ in $V$} \Comment{$O(n)$}
                \If{$v$ is burning}
                    \State \texttt{total\_cost} $\gets 0$
                    \For{$u$ in $N(v)$} \Comment{$O(n)$}
                        \State\texttt{total\_cost} $\gets$ \texttt{total\_cost} + $c(u)$
                    \EndFor
                    \State \texttt{condition\_holds} $\gets$ \texttt{True}
                    \For{$u$ in $N(v)$} \Comment{$O(n)$}
                        \If{(\texttt{total\_cost} $-c(v)$) $>b$}
                            \State\Return\texttt{False}
                        \EndIf
                    \EndFor
                \EndIf
            \EndFor
        \EndFunction
    \end{algorithmic}
    \end{algorithm}
    
```

This can clearly be verified in $O(n^2)$ (note that the second for-each $u$ is not nested in the former). Thus, we can verify that a given graph is a \nice tree in $OO(n)+(n^4)+O(n^2)=O(n^4)$ time.
