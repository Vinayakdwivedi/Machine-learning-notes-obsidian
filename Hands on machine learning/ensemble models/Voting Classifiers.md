First train multiple predictors on same dataset and find the which class have majority of votes, this is called as **hard voting classification**. This voting classifier has more accuracy than the best predictor in the estimators.
The theory here is that either you have good predictors but less in no. or you have large no. of predictors with less accuracy. Imagine it like this if you toss a coin a few time you will get a biased result(5H,3T) but as you toss it multiple time you will get closer to 50% so the probability of getting heads 50% of the time gets near to 100%.

Same with ensemble model if you train 1,000 predictors with very low accuracy around 50% which is just better than the random guesses the voting classifier can get a very high accuracy around 70-75%, this only true when all the predictors are independent of each other to do that we can use different types of algorithms to create a model.

If the predictors are able to give the probability of the class then we can find the majority class probability, which gives a better result than hard voting, this is called as **soft voting classifier**.
[[Implementation voting classifier]] 
Now the task is to get diverse predictors, we use [[Bagging and Pasting]] for that.