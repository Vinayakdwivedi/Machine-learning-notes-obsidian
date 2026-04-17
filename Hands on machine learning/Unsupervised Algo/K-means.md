K-means work on finding the distance of the points from the centroid of the class to nearest points 
k is the no. of clusters you want
```python
from sklearn import KMeans
k = 5
kmeans = KMeans(n_clusters = k)
prediction = kmeans.predict(X,y)
```

It find's it's centroids by picking random data points of the class and find the density of point in certain range then assign them the class then next random point and again assign them and do it until you get most optimal results. 
KMeans is a very fast algo which is generally linear with the no. of instances.

There is a FAST way to find the centroid by initializing them like this
```python
#approx centroids
good_init = np.array([[x1,y1], [x2,y2], [x3,y3], [x4,y4], [x5,y5]]) 
kmeans = KMeans(n_clusters =5, init = good_init, n_init =1)
```
no. of random initialization is controlled by `n_init` hyperparameter

#### Evaluating The KMeans Algo
1) [[Inertia Score]] 
2) [[silhouette score]]  