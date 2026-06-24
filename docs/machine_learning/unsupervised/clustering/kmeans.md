# K Means Clustering
Groups similar data together
- Steps in K-Means clustering:
	- _Guessing_: Make guesses for the means of every cluster.
	- _Classification_: Classify every observation in our data according to which cluster it’s most likely to be a member of, according to which mean it’s closest to.
	- _Adjustment_: Use the classifications obtained in the Classification step to calculate new estimates for the means of each cluster.
	- _Convergence_: Repeat the Classification and Adjustment steps until reaching a stopping condition.

```python
from sklearn.cluster import KMeans
kmeans = KMeans(init="random", n_clusters=3, n_init=10, max_i
ter=300, random_state=42)
kmeans.fit(allpoints)
newclass=[label+1 for label in kmeans.labels_]
makeplot(allpoints,newclass,kmeans.cluster_centers_) 
```


- in k-means clustering, we need to calculate only the means of each cluster—we don’t use covariance estimates ([[E M]]) at all in k-means clustering.