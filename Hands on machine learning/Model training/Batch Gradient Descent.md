We change the parameters very randomly at starting but after some iterations when we start to get to the bottom of the curve the randomness decreases and no. of iterations increases.
It uses the average gradient of the cost function across the full "batch" of data to take one step toward the minimum.
### The Mathematical Algorithm

For a linear model $h_\theta(x) = \theta_0 + \theta_1 x$, the cost function (Mean Squared Error) is:

$$J(\theta_0, \theta_1) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})^2$$

The simultaneous update rule for each iteration is:
1. $\theta_0 := \theta_0 - \alpha \frac{1}{m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})$
2. $\theta_1 := \theta_1 - \alpha \frac{1}{m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)}) \cdot x^{(i)}$