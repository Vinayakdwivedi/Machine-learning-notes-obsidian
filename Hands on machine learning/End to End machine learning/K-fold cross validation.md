## 📂 K-Fold Cross Validation
Instead of a single "Train/Test" split, you split the data $D$ into $k$ equal parts (folds).

- **Total Iterations:** $k$
- **In each round:** 1 fold is for **Validation**, $k-1$ folds are for **Training**.
- **Final Result:** The average of all $k$ rounds.
### 2. Why Use It?

- **No Data Waste:** Every single row gets to be in the "Test set" exactly once.
- **Reliability:** Reduces the chance that your model just got "lucky" with a specific random split.

### 3. Implementation (The "Important" Code)
```
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestClassifier

# 1. Define Model
model = RandomForestClassifier()

# 2. Run K-Fold (cv=5 means 5 folds)
# It automatically splits, trains, and evaluates
scores = cross_val_score(model, X, y, cv=5)

# 3. Final Result
print(f"Average Accuracy: {scores.mean()}")
```

### 4. Making a K fold validator
[[My-k-fold-validator]]  