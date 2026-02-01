In bagging only 63% data from the original dataset is used and the rest of the data is considered as out of the box data and is used for evaluation of the model and eventually called as out of box evaluation that 37% data is not same for all models, it can be used to evaluate the ensemble model  by averaging all the evaluation of the individual models of the ensemble model.
just set ``oob_score=True`` to get the evaluation of the ensemble 
you can get the `bag_model.oob_decision_function_` and get the result of the model on the oob evaluation for each instance either the classification or the probability depends on the base estimator 

### [[Random Patches and random subspaces]]
