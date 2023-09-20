Tags :
Zettel :  20230920-1616
Status : #triage 

-----

# Equations output for pseudocode

**Previous note:** [[]]

-----

### Questions & thoughts:

Output from Python code:

```
Eq(Derivative(〈S_0〉(t), t), -〈S_0 I_1〉(t))
Eq(Derivative(〈S_1〉(t), t), -〈I_0 S_1〉(t) - 〈S_1 I_2〉(t))
Eq(Derivative(〈S_2〉(t), t), -〈I_1 S_2〉(t))
Eq(Derivative(〈I_0〉(t), t), -3*〈I_0〉(t) + 〈S_0 I_1〉(t))
Eq(Derivative(〈I_1〉(t), t), 〈I_0 S_1〉(t) - 3*〈I_1〉(t) + 〈S_1 I_2〉(t))
Eq(Derivative(〈I_2〉(t), t), 〈I_1 S_2〉(t) - 3*〈I_2〉(t))
Eq(Derivative(〈I_0 S_1〉(t), t), 〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - 4*〈I_0 S_1〉(t))
Eq(Derivative(〈S_1 I_2〉(t), t), 〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - 4*〈S_1 I_2〉(t))
Eq(Derivative(〈I_1 S_2〉(t), t), 〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t) - 4*〈I_1 S_2〉(t))
Eq(Derivative(〈S_0 I_1〉(t), t), -4*〈S_0 I_1〉(t) + 〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t))
Eq(Derivative(〈S_1 S_2〉(t), t), 〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t))
Eq(Derivative(〈S_0 S_1〉(t), t), 〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t))
```

Output for pseudocode:

```
d[(S, 0)]/dt = - []
```


-----
 
**Consider:**


**Source:** 


**Reference:** 
