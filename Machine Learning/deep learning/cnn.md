## Convolutional Neural Networks
The human brain processes certain images that have a certain features in real life and it classifies it as such.

Yann Lecun is the father of Convolutional Neural Networks. He was a student of Geofrey Hinton.

#### How it works on a very basic level:
Input Image &#x2192; CNN &#x2192; Output Label (Image class)

![cnn1](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn1.jpg)

### Convolution
The convolution function:

![cnn2](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn2.jpg)

It is combined integration of two functions and shows how one function modifies the other.

Additional reading: [Introduction to Convolutional Neural Networks](http://cs.nju.edu.cn/wujx/paper/CNN.pdf)
by Jianxin Wu (2017).

Feature Dector (kernel of filter) with element-wise multiplication. 

![cnn3](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn3.jpg)

If one of the rows in the current fragment of the Input Image is mached up with one of the rows 
in the Feature Detector, the feature map gets 1, if two rows are mached it gets 2 and so on:

![cnn4](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn4.jpg)

When a one row of the Input Image is finished and the cursor goes down one row, it is called a **stride**.

![cnn5](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn5.jpg)

Feature Map is sometimes called a Concolved Feature or Activation Map. It is a smaller representation of the Input Image
for easier processing.

![cnn6](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn6.jpg)

### ReLU Layer
Rectified Linear Units is an additional step to apply Rectifier function to the Convolution. 
It is done to increase non-linearity in CNN.

![cnn7](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn7.jpg)

### Max Pooling (Downsampling)
Apply Spacial Invarience (CNN should have a flexibility to recognize a feature if the feature a bit tilted or bit closer 
or farther relativly to each other). The size is also reduced up to 75%.

The system applys a filter to the Feature Map and gets the highest number within the filter. After that, it moves
to the next part of the Map: 

![cnn8](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn8.jpg)

Additional Reading: [Evalution of Pooling Operations in Convolutional Architectures for Object Recognition](http://ais.uni-bonn.de/papers/icann2010_maxpool.pdf) by Dominik Scherer.

### Flattening
Take a Pooled Feaure Map and flatten it to a column, creating a vector of imputs:

![cnn9](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn9.jpg)

The whole process now looks like this:

![cnn10](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn10.jpg)

### Full Connection
Adding CNN to ANN.

![cnn11](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn11.jpg)

### Summary
The whole process:

![cnn12](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/cnn12.jpg)
