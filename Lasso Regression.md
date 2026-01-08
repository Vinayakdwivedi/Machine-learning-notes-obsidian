*Least Absolute Shrinkage*. Here we add a penalty term to the cost function to decrease the complexity of the model. But unlike ridge regression we will add the absolute value of the parameters, it's useful in feature selection.
it decrease those parameter which are not important to zero at certain value of $\alpha$ 
here is the mathematical expression.
$$
\theta = \sum_{i=0}^{n}(y_i - h(\theta)) + \alpha |\theta|
$$
Here $\alpha$ decides the level of normalization and theta is the parameter/slope.
