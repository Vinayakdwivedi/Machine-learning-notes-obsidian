Linear regression model are used to predict the data points for those data set where the variables change linearly with respect to the variable which has to be predicted. For eg:- price of house and land area.
so a linear model is just a equation which is:-
$$
\begin{aligned}
	h(\theta) = X_i \theta_i
\end{aligned}
$$
$h(\theta)$ - Hypothesis, prediction of the model.
$X_i$    - Features of the data.
$i$       - it represents the no. of variables
$\theta$      - Model parameter.
This formula is good when the mean line of the model passes through center, but to make the model flexible we introduce a bias term which gives our model flexibility along y axis. So now our equation looks like this-
$$ h(\theta) =\theta_o + \sum_{i=0}^{m}X_i \theta_i $$
We find the best value of $\theta$  where $V_\theta=0$
$$
V_\theta = (y_i-\sum_{i=0}^{m}X_i \theta_i)^2
$$
$\theta_o$  -Bias term

So here is the equation $\hat{\theta}$ ($\theta$ best) when $V_\theta=0$
#### Normal equation 
[[Derivation(linear normal eq.)]] 
$$
\hat{\theta} = (X^T X) \cdot X^T y
$$

The $\hat{\theta}$  we get is a matrix with at least 2 rows which are $\theta_o$ and $\theta_i$ ($i$ = no. of features)  
To vectorize this we use matrices for that.
$$
\begin{bmatrix}
x\\
y
\end{bmatrix}
=
\begin{bmatrix}
1 & x_1\\
1 &x_2
\end{bmatrix}
\begin{bmatrix}
 \theta_o\\
 \theta_1
\end{bmatrix}
$$
$x$ - Prediction for $x_i$
$y$ - Prediction for $x_2$
![[Pasted image 20260104003637.png]]

Scikit learn uses [[SVD(Single Value Decomposition)]] 
### [[computational complexity]] 
We can use [[Gradient Descent]] other than the <mark style="background: #D2B3FFA6;">normal equation</mark> to find the optimal parameters $\hat{\theta}$ of the model, When the data is very big.