$$= \frac{TP}{FP+TP} $$
For eg- We have two model which classifies spam emails,
![[Pasted image 20251227153610.png]]
This is the confusion matrix of Model A and Model B respectively.
Both have same accuracy but we have to pick one of them to put in production. So in real life if a email is not a spam but model has moved to spam and a mail is a spam and not moved to spam, which is more dangerous?
obviously we don't want to put a mail into spam while it's not(what if it's imp. mail), except we can accept any spam in our inbox so, we have to choose a model which has lower <mark style="background: #BB8484A6;">False Positive</mark> . This hence we need precision metric which is the measure of accuracy based on false positive which is-
$$ presicion= \frac{TP}{FP+TP} $$
