It is generally preferred over lasso regression because sometimes lasso regression sometimes can be erratic while working. 
It adds both  $l_1,$  $l_2$  norms to the cost function

Balancing the variable selection (strength of lasso regression) and grouping the correlated variables (strength of ridge regression). 
$$
\theta = \sum_{i=0}^{n}(y_i - h(\theta)) + \alpha |\theta| + \lambda |\theta|^2
$$