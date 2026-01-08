It creates a chain of arranged events which happen one after another for the data.
```
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import MinMaxScaler, OneHotEncoder
from sklearn.compose import ColumnTransformer

# Assuming 'MyCustomTransformer' is already defined
num_pipeline = Pipeline([
    ('imputer', SimpleImputer(strategy='median')),
    ('custom_tr', MyCustomTransformer()),
    ('scaler', MinMaxScaler())
])
```

to handle categorical and numerical data at the same time <mark style="background: #FFB8EBA6;">Column Transformer</mark>
 ```
# Define column groups
num_cols = ['age', 'fare']
cat_cols = ['embarked', 'sex']

# Create the full preprocessor
preprocessor = ColumnTransformer([
    ('num_path', num_pipeline, num_cols),
    ('cat_path', OneHotEncoder(), cat_cols)
])

# To use it:
# X_processed = preprocessor.fit_transform(titanic)
```