Unlike adaboosting where we change weights of the instances again and again in gradient boosting we train the model on the error  data of the previous model for example- 
```python
from sklearn.tree import DecisionTreeRegressor
tree_reg1= DecisionTreeRegressor(max_depth = 2)
tree_reg1.fit(X,y)
y2 = y-tree_reg1.predict(X)

tree_reg2 = DecisionTreeRegressor(max_depth = 2)
tree_reg2.fit(X, y2)
y3 = y2 - tree_reg2.predict(X)

tree_reg3 = DecisionTreeRegressor(max_depth = 2)
tree_reg3.fit(X, y3)

#Now we have a ensemble model with 3 decision tree
y_pred.sum(tree.predect(X_new)for tree in (tree_reg1, tree_reg2, tree_reg3))
```

We can control underfitting and overfitting using the learning_rate increasing the learning rate increases variation and decreases bias.

Decreasing the learning rate results in better regularization, called as [[Srinkage]]

We can implement early stop to find the best no. of base estimators.

#### Early Stopping using `staged_predict()` + `argmin`
```python 
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error
from sklearn.ensemble import GradientBoostingRegressor

# Split data
X_train, X_val, y_train, y_val = train_test_split(X, y)

# Train model with large number of trees
gbrt = GradientBoostingRegressor(max_depth=2, n_estimators=120)
gbrt.fit(X_train, y_train)

# Validation error at each stage
errors = [
    mean_squared_error(y_val, y_pred)
    for y_pred in gbrt.staged_predict(X_val)
]

# Best number of trees
bst_n_estimators = np.argmin(errors) + 1

# Train final model
gbrt_best = GradientBoostingRegressor(
    max_depth=2,
    n_estimators=bst_n_estimators
)
gbrt_best.fit(X_train, y_train)
```
#### Early Stopping using `warm_start=True` (Manual Stop)
```python
from sklearn.ensemble import GradientBoostingRegressor
from sklearn.metrics import mean_squared_error

gbrt = GradientBoostingRegressor(max_depth=2, warm_start=True)

min_val_error = float("inf")
error_going_up = 0

for n_estimators in range(1, 120):
    gbrt.n_estimators = n_estimators
    gbrt.fit(X_train, y_train)

    y_pred = gbrt.predict(X_val)
    val_error = mean_squared_error(y_val, y_pred)

    if val_error < min_val_error:
        min_val_error = val_error
        error_going_up = 0
    else:
        error_going_up += 1
        if error_going_up == 5:
            break
```
The second method is more efficient as it saves time and compute power.
use ==`subsample= 0.25`==to train each tree on just 25% random instances, this way we can decrease the training time and it is converted to *Stochastic Gradient boosting*. 

A more efficient *Gradient Boost* is **[[XGBOOST]]** 