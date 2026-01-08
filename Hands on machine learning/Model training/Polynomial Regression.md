When our data can not fit through a straight line, like our data(variables) has a weird relation between them like for example- parabolic or some other shape.
![[Pasted image 20260106020503.png]]
### Mechanism
Polynomial regression is just linear regression just there is one more input which is just the existing feature just its square or any other degree term. See, it's like parameters doesn't changes only features change, its just feature engineering.
$$
h(\theta) = \theta_o + \theta_1 x +\theta_2 x^2
$$
The power defines the curvature or the degree of freedom our model have, like how much our model can fit to the data.
$$
\begin{bmatrix}
x \\
y
\end{bmatrix}
=
\begin{bmatrix}
1 & x \\
1 & x^2
\end{bmatrix}

\begin{bmatrix}
\theta_o \\
\theta_1
\end{bmatrix}
$$

### Learning curves
A regression model's 
A model has degrees which decide weather the model will overfit or under fit. 
we can check that weather the model underfits or over fit by plotting the graph between data quantity versus performance measure. 

$\text{aqua line - validation error}$
$\text{blue line - training error}$
![[Pasted image 20260106202630.png]]
### Bias Variance Trade Off
#### There are actual three type of errors in model

*Irreducible Error-* When the data is not good has too much noise.

*Bias-* When the data cannot fit through a straight line and we choose linear model then it will underfit the data and the gap between the training error and validation error increases. When model perform poor on both training set and validation set.

*Variance-* Variance is when a model is very sensitive to the data, it memorizes the data and also captures all the noise in the data. When the model perform good on training set but poor at validation set it's called as overfitting.

To avoid overfitting we normalize the data, using two methods which are-
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]