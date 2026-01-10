``` Python

**#creating our own k-fold cross validator
from sklearn.model_selection import StratifiedKFold
from sklearn.base import clone

strat_folds = StratifiedKFold(n_splits = 3, random_state = 42, shuffle = True)
iter_ = 0
sum_accuracy = 0

for train_image , test_image in strat_folds.split(training_images_flat, training_labels_5):
    cloned_clf = clone(sdg_classify)
    train_image_fold = training_images_flat[train_image]
    train_labels_fold = training_labels_5[train_image]
    test_image_fold = training_images_flat[test_image]
    test_labels_fold = training_labels_5[test_image]
    

    cloned_clf.fit(train_image_fold, train_labels_fold)
    y_pred = (cloned_clf.predict(test_image_fold))
    add = sum(y_pred == test_labels_fold)
    accuracy = add/ len(y_pred)
    print(accuracy)
    
    sum_accuracy = sum_accuracy+accuracy
    
    iter_ =iter_ +1
print("your accuracy based on cross validataion is" ,sum_accuracy/iter_)
**
```

## What actually happens (truth bomb 💣)

When you create this:

`skfolds = StratifiedKFold(n_splits=3, random_state=42)`

And then call:

`skfolds.split(training_images, training_labels_5)`

👉 sklearn does this **ONCE** internally:

1. Looks at **all indices**: `0 ... N-1`
2. Groups them **by class label** (because stratified)
3. Shuffles indices (if enabled)
4. **Pre-divides** them into `K` disjoint test sets
So internally it becomes something like:
```
Test Fold 1 → indices A
Test Fold 2 → indices B
Test Fold 3 → indices C
```

- `X_train` → number of samples
- `y_train_5` → class labels
Since this is **[[stratified sampling]]**, it uses `y_train_5` to:
- Preserve class ratios in each fold
Example:

`Full data → 90% class 0, 10% class 1 Each fold → ~90% class 0, 10% class 1`

Without `y_train_5`, stratification is impossible.