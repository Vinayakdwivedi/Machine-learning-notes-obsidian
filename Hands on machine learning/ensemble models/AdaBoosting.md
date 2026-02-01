It trains a weak learner(accuracy of 50-51%) first, then increases the weights of the misclassified instances then passed to another weak learning model, once all the predictors are trained ensemble predicts it just same as bagging algorithm but this time the predictors have different weights.
Each instance iii is assigned a weight:
 
$wi(1)=1mw_i^{(1)} = \frac{1}{m}wi(1)​=m1​$ 

Train predictor jjj on the **weighted dataset**.

Compute its **weighted error rate**:
$$
r_j =
\frac{
\sum_{i=1}^{m} w_i^{(j)} \cdot \mathbf{1}\left(\hat{y}_j^{(i)} \ne y^{(i)}\right)
}{
\sum_{i=1}^{m} w_i^{(j)}
}
$$

**Intuition**

- Errors on **high-weight points matter more**
    
- A predictor that fails on “important” samples is penalized heavily
The predictor’s influence is:

$αj=ηlog⁡(1−rjrj)\alpha_j = \eta \log\left(\frac{1 - r_j}{r_j}\right)αj​=ηlog(rj​1−rj​​)$
Where:
- $η$ = learning rate (defaults to 1)
 **Intuition**
- Low error → large $αj\alpha_jαj​$
- Random guessing → $αj≈0\alpha_j \approx 0αj​≈0$
- Worse than random → $αj<0\alpha_j < 0αj​<0$

So:
> Better predictors get more voting power

For each instance iii:

$$
w_i^{(j+1)} =
\begin{cases}
w_i^{(j)} & \text{if } \hat{y}_j^{(i)} = y^{(i)} \\
w_i^{(j)} \exp(\alpha_j) & \text{if } \hat{y}_j^{(i)} \ne y^{(i)}
\end{cases}
$$


Then normalize weights so they sum to 1.
**Intuition**
- Correctly classified → weight unchanged
- Misclassified → weight increased
- Next predictor is **forced to focus on mistakes**

scikit-learn uses **SAMME** algo which is same as adaboost but also for multiclass and a different algo **SAMMER -R stands for real** it is used when base estimator provides the probability of the class

```python
from sklearn.ensemble import AdaBoostClassifier
from sklearn.tree import DecisionTreeClassifier

model = AdaBoostClassifier(
    estimator=DecisionTreeClassifier(max_depth=1),
    n_estimators=50,
    learning_rate=1.0
)

model.fit(X_train, y_train)
```

```python
model.estimator_weights_   # α_j values
model.estimator_errors_    # r_j values
```