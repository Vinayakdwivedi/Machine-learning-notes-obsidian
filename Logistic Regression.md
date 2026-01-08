Logistic regression(logit regression) works by computing the probability that the instance belong to which class(eg- either the mail is spam or not). If probability >0.5 then its in positive class else in negative

#### How to predict the probability
###### Mechanism
$$
\hat{y} = \sum_{i=0}^{n} \sigma(x^T \theta ) 
$$
here $\sigma$ is the sigmoid function which is 
$$
\sigma(t) = \frac{1}{1+ e^{-t}}
$$
![[Pasted image 20260108200945.png]]
```
The score t is called the logit, as it is derived from the inverse of the logistic function. So if we take the inverse log of the logistic function(p) we get t
```
$$
logit(p) = log(\frac{p}{1-p})
$$
so our probability function of the regressor looks like 
$$
\hat{y} = \frac{1}{1+ e^{-x^T \theta}}
$$
The instances which have the probability greater than $0.5$  are listed as positive class and less than that are to the negative class.