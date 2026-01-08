Ridge regression is a method use to normalize the mode to prevent. 
The equation says that if the slope is very big then a slight change in the feature will affect the prediction greatly, that's the case for overfitting. 
And if the slope is very less then small changes in features will not affect the prediction, which is the case for under fitting.
$$
h(\theta)= \theta_0 + \theta_1 x
$$
`higher the slope = higher the chance of over fitting`
so we introduce an extra term in the cost function which make sure that the model with lower slope is preferred as a choice because it is less likely to get overfit. Same goes for higher dimension data.
$$
J(\theta)
$$
#### Mathematical Expression
$$
h(\theta) = \sum_{i=0}^{m} (y_i - h(\theta)) + \lambda (\sum_{i=0}^{n}\theta_i^2)
$$
$\text{m - slope of the line}$ 
$\lambda - \text{hyper parameter, which control the intensity of normalization}$ ]
After simplifying the above equation we get a closed form equation.
Closed form equation of ridge regression 
 $$
 \theta = (X^T X + \alpha A)^{-1} X^T y
 $$
 