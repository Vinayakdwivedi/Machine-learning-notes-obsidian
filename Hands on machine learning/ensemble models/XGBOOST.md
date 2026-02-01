XGBoost = Optimized Gradient Boosting with hardcore performance + regularization

```python
from xgboost import XGBRegressor

model = XGBRegressor(
    n_estimators=200,
    max_depth=4,
    learning_rate=0.05,
    subsample=0.8,
    colsample_bytree=0.8
)

model.fit(X_train, y_train)
pred = model.predict(X_test)
```
