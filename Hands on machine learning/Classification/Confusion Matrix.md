Why K-Fold fails- let's say our model, which has 90% accuracy on our k fold cross validation (which predicts weather the image is 5 or not), what if our model just said false to every image that we provided and also that only 10% of that testing data had the letter 5 so our new model will be 90% accurate because our 90% of data is not, remember what we did with our test set and to prevent it we used [[K-fold cross validation]] but this time we will be doing same to our model but with k-fold prediction not k-fold data 
![[Pasted image 20251227152952.png]]

We're using scikit learns 'cross_val_predict' class which will return prediction matrix(confusion matrix) instead of the accuracy.

Now we use two type of evaluation for our model which are-
1) Accuracy of confusion matrix
`Accuracy of confusion matrix =` $$ \frac{TP}{TP+FP+FN+TN} $$
But let's say your data is poorly distributed like you want to predict terrorist which is just 1 in 1,000
so if our model just said no to all the data then our data will be 99.99% accurate according to above equation, so to prevent this we introduce some new metric to find the accuracy of the model.
2) [[Precision]]
3) [[Recall]]
4) [[F1 score]]
type 1 error - With high false positive
type 2 error - With high false negative
#### TL;DR
<mark style="background: #FFB8EBA6;">Precision</mark>- tells the ratio of that our model said it was true and it was with that our model said true but not. `*Higher the precision, our model will` <mark style="background: #FFB86CA6;">less say true</mark>
*If you're problem is more affected by type 1 error then chose high precision*.

<mark style="background: #FFB8EBA6;">Recall</mark> - tells the ration of that our model said it was true and it was with that our model said false but it was true. `Higher the recall, our model will` <mark style="background: #FFB86CA6;">less say false</mark>  
*If you're problem is more affected by type 2 error the chose high recall*.

```python
from sklearn.metrics import confusion_matrix
from sklearn.model_selection import cross_val_predict

y_pred = cross_val_predict(model, X_train, Y_train, cv=n(3,4,5..))
cnf_mat = confusion_matrix(Y_true, Y_pred, label='')
```
