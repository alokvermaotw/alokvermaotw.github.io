# Steps in KNN:
- Choose a point p you want to make a prediction about for a target variable.
- Choose a natural number, k.
- Find the k nearest neighbors to point p in your dataset.
- The mean target value of the k nearest neighbors is the prediction for the
target value of p.


- k-NN is nothing
more than a simple idea that children and even interns already intuitively
grasp: that if things resemble each other in some ways, they’re likely to
resemble each other in other ways. If things live in the same neighborhood,
they might be similar to each other.

# How KNN is different to K Means?
- KNN is supervised ml used for classification and Regression problems. it use to classify the new dataset based on the classes of their nearest neighbor in their training dataset.
- While [[K Means]] is an Unsupervised ML used for clustering data points based on their similarity. works by randomly selecting K data points as initial centroid of the cluster, then it assigns each data points to the nearest centroids and recalculate the centroid based on the mean data point of each cluster. the process repeated until centroid no longer change.