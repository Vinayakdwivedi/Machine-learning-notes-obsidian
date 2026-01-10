`GridSearchCV` (Grid Search Cross-Validation) is a **hyperparameter tuning** technique that performs an **exhaustive search** over a specified range ("grid") of parameter values to find the optimal combination for a given machine learning model

How it Works
1. **Define the Parameter Grid**: A dictionary is created where keys are the hyperparameter names (e.g., `'C'`, `'kernel'`, `'max_depth'`) and values are lists of settings to try for each parameter.
2. **Cross-Validation**: For each combination in the grid, the data is split into multiple folds (e.g., 5-fold cross-validation is the default in scikit-learn). The model is trained on some folds and validated on the remaining fold, rotating the validation fold each time.
3. **Evaluation**: A performance metric (e.g., accuracy, F1 score, R-squared) is computed for each fold, and the average score is used to represent that parameter combination's performance.
4. **Select the Best Model**: After testing all combinations, `GridSearchCV` selects the set of hyperparameters that yielded the highest average score during cross-validation.
5. **Refit**: The final model is then typically refit on the entire training dataset using these best-found parameters.