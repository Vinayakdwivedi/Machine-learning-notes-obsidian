Another method of making a ensemble model is using a staking the idea here is that we train a new model which is trained for selecting the `base_estimators`, unlike bagging which choose the max class predicted.

```python
when model_1 is wrong:
     model_6 is also wrong
     but model_2 is correct
```

The new model find these patterns and predict.

![[Pasted image 20260130133103.png]]
# Real Training Process

---

## Step 1 — K Fold Training for Base Models

For each fold:

`Train on Fold Train Predict on Fold Validation`

Collect predictions for ALL samples.

Now you have:

`New dataset = Base model predictions`

---

## Step 2 — Train Meta Model

Meta model learns:

`Base Predictions → True Labels`

---
## Step 3 — Final Production Setup

- Train base models on full data   
- Keep meta model trained

Done.