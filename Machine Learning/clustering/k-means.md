## K-Means
K-means allows for clustering your data.

![k-means1](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/km1.jpg)

1. Choose the number K of clusters
2. Select at random K points, the centroids
3. Assign each data point to the closest centroid (forms K clusters)
4. Compute and place the new centroid of each cluster
5. Reasign each data point to the new closest centroid
- Repeat step 5 or finish if no chages happend.

Random Initialization Trap - the selection of K points (centroids) can dictate the positioning of the clusters.
To prevent this use enhancement to the previous algorithm called K-Means++. This enhancement is usually included
into the most libraries for R and Python.

Use Elbow Method to choose the right number of clusters based on WCSS metrics.
