To have independent predictors we can either use different algorithms or we can train same model on variety of data so here comes bagging and pasting.
**Bagging** (Bootstrap aggregation) - Sampling the data with replacement which means 
using the same dataset to train all the models, like using same dataset for training multiple predictors(Random Forest). It is good for reducing variance on trading bias.

**Pasting** -Sampling the data without replacement, using different random data points from same dataset to to train models.

![[Pasted image 20260129135132.png]]
after training aggregation is done- 
Aggregation is is typically the statistical mode(most frequent prediction *hard voting*)

Predictors can be trained on parallel cpu cores or even parallel computers.
Bootstrapping introduces diversity in the subset data on which each predictor is trained so it ends up with more bias than pasting and reduced variance but mostly bagging ends up better, you can check by cross-validation.
Now to evaluate the ensemble model.
[[Out Of The Box Evaluation]] 
A popular example of  ensemble learning is [[Random forest]] 