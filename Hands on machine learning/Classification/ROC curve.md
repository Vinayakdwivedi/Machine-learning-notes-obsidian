Here we have two metric which are *True Positive Rate*(TPR)and *False Positive Rate*(FPR)
![[Pasted image 20251227152952.png]]
$$ TPR = \frac{TP}{TP+FN}$$
$$FPR = \frac{FP}{FP+TN}$$
TPR shows the actual benefit of the model.
FPR shows the actual cost(loss) of the model.

$$ TPR \propto FPR $$
 
We need to make TPR closer to 1 and FPR closer to 0, lets draw a curve between both,
less value of threshold give more TPR and FPR and vice versa, we need to get the value of threshold which makes the both values close to top left corner.
![[Pasted image 20251228141630.png]]