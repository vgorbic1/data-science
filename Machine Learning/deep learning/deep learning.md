## Deep Learning
Deep Learning is the most exciting and powerful branch of Machine Learning. Deep Learning models can be used for a 
variety of complex tasks:
- Artificial Neural Networks for Regression and Classification
- Convolutional Neural Networks for Computer Vision
- Recurrent Neural Networks for Time Series Analysis
- Self Organizing Maps for Feature Extraction
- Deep Boltzmann Machines for Recommendation Systems
- Auto Encoders for Recommendation Systems

Geoffrey Hinton is the godfather of Deep Learning.

The model of "shallow" learning:

![sl](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/sl.jpg)

Deep Learning model:

![sl2](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/sl2.jpg)

Neuron is a basic building block of a Neural Network.

![perceptron](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/perceptron.jpg)

Gradient Descent (Batch Gradient Descent) is used to adjust weights in a bulck and find the best convex Cost Function fit:

![gradient descent](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/gd.jpg)

Stochastic Gradient Descent is used to adjust weights in each row and find best non-convex Cost Function fit:

![stochastic gradient descent](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/sgd.jpg)

Training the ANN with Stochastic Gradient Descent
1. Randomly initialize the weights to small numbers close to 0, but not 0.
2. Input the first observation of your dataset in the input layer, each feature in one input node.
3. Forward-Propagation: from left to right, the neurons are activated in a way that the impact of each neuron's activation
is limited by the weights. Propagate the activations until gettint the predicted resul y<sup>^</sup>.
4. Compare the predicted result to the actual result. Measure the generated error.
5. Back-Propagation: from right to left, the error is back-propagated. Update the weights according to how much they are
responsible for the error. The learning rate decides by how much we update the weights.
6. Repeate Steps 1 to 5 and update the weights after each observation (Reinforcement Learning). Or:
Repeat Steps 1 to 5 but update the weights only after a batch of observations (Batch Learning).
7. When the whole training set passed through the ANN, that makes an epoch. Redo more epochs.




