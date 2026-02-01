```python
_class_ sklearn.tree.DecisionTreeClassifier
```

```python
gcv = GridSearchCV(clone(dt), param_grid)
m = gcv.fit(X_train, y_train)
```

- **criterion**{“gini”, “entropy”, “log_loss”}, default=”gini”
- **splitter**{“best”, “random”}, default=”best”
	The strategy used to choose the split at each node. Supported strategies are “best” to choose the best split and “random” to choose the best random split.
- **max_depth** : int, default=None 
	The maximum depth of the tree. If None, then nodes are expanded until all leaves are pure
	**max_depth** $\propto$ overfitting, underfitting
- **min_samples_split**
- **min_samples_leaf**
- **min_weight_fraction_leaf**
- **max_features**
- **random_state**
- **max_leaf_nodes**
- **min_impurity_decrease**