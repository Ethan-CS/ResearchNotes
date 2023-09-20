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
Eq(Derivative(〈S_0〉(t), t), -\beta*〈S_0 I_1〉(t))
Eq(Derivative(〈S_1〉(t), t), -\beta*〈I_0 S_1〉(t) - \beta*〈S_1 I_2〉(t))
Eq(Derivative(〈S_2〉(t), t), -\beta*〈I_1 S_2〉(t))
Eq(Derivative(〈I_0〉(t), t), \beta*〈S_0 I_1〉(t) - \gamma*〈I_0〉(t))
Eq(Derivative(〈I_1〉(t), t), \beta*〈I_0 S_1〉(t) + \beta*〈S_1 I_2〉(t) - \gamma*〈I_1〉(t))
Eq(Derivative(〈I_2〉(t), t), \beta*〈I_1 S_2〉(t) - \gamma*〈I_2〉(t))
Eq(Derivative(〈I_0 S_1〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \beta*〈I_0 S_1〉(t) - \gamma*〈I_0 S_1〉(t))
Eq(Derivative(〈I_1 S_2〉(t), t), \beta*〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t) - \beta*〈I_1 S_2〉(t) - \gamma*〈I_1 S_2〉(t))
Eq(Derivative(〈S_0 I_1〉(t), t), -\beta*〈S_0 I_1〉(t) + \beta*〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \gamma*〈S_0 I_1〉(t))
Eq(Derivative(〈S_1 I_2〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \beta*〈S_1 I_2〉(t) - \gamma*〈S_1 I_2〉(t))
Eq(Derivative(〈S_1 S_2〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t))
Eq(Derivative(〈S_0 S_1〉(t), t), -\beta*〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t))
```

Output for pseudocode:

```
d[(S, 0)]/dt = -\beta*[(S, 0), (I, 1)]
d[(S, 1)]/dt = -\beta*〈I_0 S_1〉(t) - \beta*〈S_1 I_2〉(t))
d[(S, 2)]/dt = -\beta*〈I_1 S_2〉(t))
d[(I, 0)]/dt = \beta*〈S_0 I_1〉(t) - \gamma*〈I_0〉(t))
d[(I, 1)]/dt =  \beta*〈I_0 S_1〉(t) + \beta*〈S_1 I_2〉(t) - \gamma*〈I_1〉(t))
d[(I, 2)]/dt =  \beta*〈I_1 S_2〉(t) - \gamma*〈I_2〉(t))

Eq(Derivative(〈I_0 S_1〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \beta*〈I_0 S_1〉(t) - \gamma*〈I_0 S_1〉(t))
Eq(Derivative(〈I_1 S_2〉(t), t), \beta*〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t) - \beta*〈I_1 S_2〉(t) - \gamma*〈I_1 S_2〉(t))
Eq(Derivative(〈S_0 I_1〉(t), t), -\beta*〈S_0 I_1〉(t) + \beta*〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \gamma*〈S_0 I_1〉(t))
Eq(Derivative(〈S_1 I_2〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t) - \beta*〈S_1 I_2〉(t) - \gamma*〈S_1 I_2〉(t))
Eq(Derivative(〈S_1 S_2〉(t), t), -\beta*〈I_0 S_1〉(t)*〈S_1 S_2〉(t)/〈S_1〉(t))
Eq(Derivative(〈S_0 S_1〉(t), t), -\beta*〈S_0 S_1〉(t)*〈S_1 I_2〉(t)/〈S_1〉(t))
```


-----
 
**Consider:**


**Source:** 


**Reference:** 
