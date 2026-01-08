### Custom Transformers
Sometimes we want to create some functions or classes which does some transformations, so we can add them to scikit learn pipeline which will give some functionalities of scikit learn like 
[[Grid search CV]] is a class in scikit learn.

### let's create one
# Goal of this Custom Transformer

We will build a transformer that:

- Takes numeric data
- Adds **one new feature**
- That feature is **optionally enabled**
- Works with **Pipeline**
- Works with **GridSearchCV**
- Respects **all sklearn rules**
   
Example idea (simple but powerful):

> Add a feature called  
> **`feature_sum = column_0 + column_1`**

```
import numpy as np
from sklearn.base import BaseEstimator, TransformerMixin

class SumFeatureAdder(BaseEstimator, TransformerMixin):
    """
    Custom transformer that optionally adds
    a new feature: sum of first two columns
    """

    def __init__(self, add_sum_feature=True):
        # 1️⃣ Hyperparameter (must be stored exactly like this)
        self.add_sum_feature = add_sum_feature

    def fit(self, X, y=None):
        # 2️⃣ No learning happens here
        # Required for sklearn compatibility
        return self

    def transform(self, X):
        # 3️⃣ Feature engineering happens here
        
        # Compute new feature
        sum_feature = X[:, 0] + X[:, 1]

        if self.add_sum_feature:
            # Add new column
            return np.c_[X, sum_feature]
        else:
            # Return original data unchanged
            return X

```

In scikit-learn, `__init__()` is not just a constructor — it is the **contract** that makes your estimator tunable, clonable, reproducible, and pipeline-safe.

Data Transformation can be tricky, we use [[Data Pipelines]] for transforming data easily