## Hierarchical Clustering (HC)
There are two approaches in HC:
- Agglomerative
- Divisive (reverse of agglomerative)

### Agglomerative HC
1. Make each data point a single-point cluster to form N-cluster
2. Take the two closest data points and make them one cluster to form N-1
3. Take the two closest clusters and make them one cluster to form N-2
4. Repeat step 3 until there is only one cluster

Dendogram - is a memory of HC, which keeps all steps of the algorithm:

![dendogram]()

5. Set the freshold of dissimilarity among the clusters. To find the freshold look at the largest distance and
devide it in a half.

![hc]()

The number of clusters will depend on how high the freshold is set.
