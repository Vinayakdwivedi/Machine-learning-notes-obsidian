| b**Feature**            | **Logistic Regression**          | **SVM**                              | **Decision Tree**                           |
| ----------------------- | -------------------------------- | ------------------------------------ | ------------------------------------------- |
| **Model Type**          | Probabilistic                    | Geometric                            | Hierarchical/Rule-based                     |
| **Outlier Sensitivity** | Sensitive (can skew the sigmoid) | Robust (only support vectors matter) | Very Robust (outliers rarely affect splits) |
| **Feature Scaling**     | Not strictly required, but helps | **Required** (distance-based)        | **Not Required**                            |
| **Interpretability**    | High (coefficients show impact)  | Low (hard to explain hyperplanes)    | High (can be visualized as rules)           |
| **Risk of Overfitting** | Low (unless features >> samples) | Moderate (controlled by C and Gamma) | **High** (requires pruning or `max_depth`)  |