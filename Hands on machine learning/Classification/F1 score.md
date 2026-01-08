When we have a problem which does not fit into recall or in precision, like a classification of dog and cat, so we define a new metric for this which is harmonic mean of both precision and recall.

$$ F1 = \frac{2PR}{P+R} $$
P = precision
R = recall
The answer of this metric is in the side of the lower value.

### Precision Recall Trade Off-
Model provides a precision score for each instance provided by a decision function. The instances which gives greater precision score than threshold value then it fall's into positive(1) if not then negative(0) output.
$$ presicion \propto \frac{1}{Recall} $$
We can plot the curve for these using this code-
![[Pasted image 20251227190210.png]]
Increasing the threshold increases the Precision and decreases the Recall value 
But it is possible that, rarely the precision score decreases, but recall always decreases.
We can use precision recall values to set the correct threshold.
But there is one more method for setting our threshold which is [[ROC curve]] 