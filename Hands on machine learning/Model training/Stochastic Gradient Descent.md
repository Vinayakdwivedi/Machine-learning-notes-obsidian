In this we take the parameters with greater randomness the loss function changes with a large difference. It is immune to local minima's. Imagine it's like rolling a tire from a mountain instead of a person descending from the mountain(like in [[Batch Gradient Descent]]).

It is faster than Batch gradient descent but less optimal results. sometimes if the iteration rate is very large the model will deviate from the result by large values and eventually can skip the global minima. *It's learning rate decides how accurate the model is* 
A major problem with this is that it gets stuck near to the bottom that means when it get's very close to the optimum it just hop around doesn't gives the optimum result, but by decreasing learning rate eventually will solve this issue.

Before using this model ensure that your data is well distributed/Shuffled.
![[Pasted image 20260105022903.png]]
![[Pasted image 20260105022933.png]]

sklearn has a class SGDRegressor class for linear regression and SGDClassifier for classification.