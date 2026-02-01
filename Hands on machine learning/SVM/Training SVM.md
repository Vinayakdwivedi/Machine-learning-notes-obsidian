We need to create a loss function to train our model.
So to have a optimal result we need to decrease the distance between the two support vectors which is 
$$
d = min (\frac{||w||}{2})
$$
 to show this hard margin eq as constrained optimization problem.
 
 Minimize  $\frac{1}{2}w^Tw$
 subject to  $t^{i}(w^tx+b) >=1$ 
 
For soft margin SVM we introduce a new error term which is $\zeta$ (zeta) which tells the classifying error(is the class correctly classified)

$$
\frac{1}{2} w^T w + C \sum^{m}_{i=1} \zeta^i
$$

subjected to  $t^i (w^Tx+b)>=1-\zeta$  and  $\zeta^i >=0$  for  $i=1,2,..,m$ 

### Quadratic Programming
For solving equation like the one above having constraints we use quadratic programming. there are many methods to solve quadratic problems just pick one.

Book for **QP**
- chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf