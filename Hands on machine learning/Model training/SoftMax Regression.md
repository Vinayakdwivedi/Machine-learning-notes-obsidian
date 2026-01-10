This is used when we have more than two classes in the dataset.
eg- we have a dataset with more than 3 classes so we will perform certain steps to perform soft max regression
Data has cgpa and  IQ and there are three classes- 1)placement, 2)not placement, 3)opt out

- Step 1) first transform the classes using one-hot-encoding into 0 and 1.
- Step 2) There will be five columns and create classifying model for each class, (either the instance belong to the class or not) now our three model predict these placement 0|1, not placed 0|1, opt out 0|1
![[Pasted image 20260109155653.png]]

- Step3) All the three models which will be written in this form- 
	$Z_1 =AW_1+BW_2+C$ 
- Now we will predict the probability of each $Z_1,Z_2,Z_3$ using this sigmoid function separately 
$$
\sigma(y_n) = \frac{e^{z_n}}{e^{z_2}+e^{z_3}+e^{z_1}...+e^{z_n}}
$$
n is a model.
More efficiently we can use this loss function instead of step 3, it is a cross entropy function.
$$
L = -\frac{1}{m} \sum_{i=1}^{m} \sum_{k=1}^{k} Y_K^i log(\hat{y}_k^{(i)})
$$
![[Pasted image 20260109220728.png]] 
![[Pasted image 20260109220904.png]]
