## Decision Tree
There are two types of trees:
- Classification trees.
- Regression trees.

### Regression Tree
Regression tree is a bit more complicated than classification tree.
Let's have two independent variables X<sub>1</sub> and X<sub>2</sub> represented in this chart:

[chart]()

We need to find dependent Y, which is in the third dimension.

Algorithm will split the plot in segments (leafs) according to Information Entropy.

[chart2]()

Algorithm then cretes a tree based on those segments:

[chart3]()

To predict Y, algorithm gets average of all independent values in this particular segment. 
