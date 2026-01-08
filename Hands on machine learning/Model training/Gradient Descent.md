Gradient Descent is based on a basic concept where we have try to decrease the cost function of our function, by changing the model parameter(y intercept, slope) randomly so to decrease the cost function like Mean Square Error until the cost function is at its minimum. 
It's like I'am on a mountain and want to get down to the valley but I can't look for the peak so i will check where the ground is steep then take my step until i reach to bottom.

It is different from the normal equation, as it is used when the data is very large and to optimize the process of finding the parameters. 

#### The concept
1) Random parameters are first selected, and those para meters which results in lowering the cost function are considered.
2) Then the algo choose those parameters which decrement the cost function, then again some parameter which decrease the $\hat{\theta}$ and so on until the cost function is minimum. 

 ![[Pasted image 20260105013839.png]]
 ![[Pasted image 20260105021220.png]]
This algorithm will not work if there are local minima

 To find optimal parameters we have different kind of gradient descent methods like-
  1) [[Batch Gradient Descent]]  
  2) [[Stochastic Gradient Descent]]
  3) [[Mini Batch Gradient Descent]] 