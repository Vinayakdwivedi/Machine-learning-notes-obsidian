Now what should be the optimal no of clusters I mean what should be the best value of k, inertia fails to do this because as you increase the k it keeps decreasing. Instead we use mean *Silhouette Coefficient* -
$$
\frac{b-a}{max(a,b)}
$$
$a-\text{mean distance of other instances in the cluster}$
$b - \text{mean distance of the instances of other nearest cluster}$

```mermaid
xychart-beta
      title "value k vs inertia"
      x-axis"value of k" [1,2,3,4,5,6,7,8]
      y-axis "Inertia" 200 --> 1200
      line [1108, 804, 500, 300, 244, 233, 230, 227]
```

**`Just plot a silhouette diagram and find the best value of k`**
![[Pasted image 20260206001309.png]]