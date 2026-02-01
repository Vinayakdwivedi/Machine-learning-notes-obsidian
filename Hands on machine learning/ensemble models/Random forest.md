It is an ensemble of multiple decision trees to produce more accurate and stable predictions than a single tree, on the trade of bias and decrease in variance 
```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import make_classification
# 1. Generate dummy data
X, y = make_classification(n_samples=100, n_features=4)
# 2. Initialize and fit
rf = RandomForestClassifier(n_estimators=100)
rf.fit(X, y)
# 3. Predict
predictions = rf.predict(X[:2])
```

Same implementation using bagging classifier
```python
from sklearn.ensemble import BaggingClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.datasets import make_classification
# 1. Generate dummy data
X, y = make_classification(n_samples=100, n_features=4)
# 2. Initialize Bagging with a Decision Tree base
bagging = BaggingClassifier(estimator=DecisionTreeClassifier(), n_estimators=100)
bagging.fit(X, y)
# 3. Predict
predictions = bagging.predict(X[:2])
```

### [[Feature selection]]
