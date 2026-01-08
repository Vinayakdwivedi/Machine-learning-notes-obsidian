```
from sklearn.preprocessing import OrdinalEncoder
ordinal = OrdinalEncoder()
s = ordinal.fit_transform(df['catagorical_column'])
s[:10]
```
When to use Ordinal Encoding (Label Encoding):

- **Ordinal Data:** For features with a natural order (e.g., Small, Medium, Large; Low, Medium, High).

- **Memory Efficiency:** When dealing with high-cardinality features (many unique values) or memory constraints, as it uses fewer features.

- **Tree-Based Models:** Often works well with tree-based models (like Decision Trees, Random Forests) as they inherently handle feature importance without being as misled by the numerical values.