# Deep Laerning 1 - Hugo Larochelle 
Topics available online on U Sherbrooke website.

## Neural Networks
### Introduction 
* Neurons
* Single hidden layer neural network
	* Can represent almost any function with enough neurons 
* Multilayer neural network 
* Activation functions 
	* Sigmoid
	* Hyperbolic
	* ReLU
	* Softmax: used in the output layer for multi-class classification p(y=c|x). The values sum up to 1. 
* Flow graph
	* Modularization of the networks
	* Easier automatic ack prop

### Training Feedforward Neural Networks
* Learning is cast as optimization: loss function + regularization 
* Stochastic Gradient Descebet (SGD)
	* init thetas
	* for N epoch: compute delta, add delta * learning rate (theta += theta + learning rate * delta)
	* delta is the gradient of the loss function and the regulization loss
	* What is required: 
		* Loss function 
		* Procedure to obtain the gradietn 
		* initialization method 
		* reglaization 
* Loss function 
	* maximing the probabiliy of the true class
	* In practive: l(f(x), y) = -log(f(x))_y
	* We take log to simlify for numerical stability and math simplicity, sometimes reffered to as cross entropy.
* Back prop
	* Use chain rule to efficiently compute gradients, top to bottom
	* compute output gradietn before activation: delta [-log(f(x))_y] = -(e(y) - f(x))
	* compute gradeints of hiddent layer parameter
	* Check the slides
	* If the wights or partial derivatives of activation is close to zero(saturation), then the layers down will have a very small changes. These are the things for debugging neural networks. 
	* If you see small gradients:
		* Norm of the gradient
		* Saturation of activations
		* If all hidden units are changing in the same direction it proabaly means the weights have not been randomized at eh beggining.
		* If the loss is going up, the learning rate is too high.
		* Sometimes we wait for few epochs, if still the losss is going up we should do something about the learnign reate. 
	* Partial derivates:
		* In ReLUs the partial derivate is either 1 or 0. That's why they make the optimziation easier. 
	* Automatic diff based on the flow graph
* L2 regulization
	* Encouraging small weights
* Initiliazation:
	* Biases: Usually init to zeros
	* Weights: 
		* Can't init to zeros
		* Can't init to same values 
		* Use a sampling recipe 
* Hyperparameters: to find the best config of hyperparameters
	* Grid search 
	* Random search: Better and more efficient than grid search 
	* Bayesian optimization or sequential model based optimization
* Early stopping:
	* Stop teh training when validation set increases -> best compromise between overfitting and underfitting

### Tricks of the Trade
* Normalization of data
* Decaying the learning rate
* Using mini-batches 
	* The updates are less noisy
	* It uses HW more efficiently (matrix-matrix multiplication)
	* Can use an exponential average of prev gradients: dec(t) = delta + beta * dec{t-1}
* Updates with adaptive laerning rates: Adam, Adagrad, RMSprop
* Gradient checking 
	* to debug the implementation of fprop/bprop, use finite difference approximation to check the gradients 
	* When the loss is going down, it doesn't neccessarily mean there are no bug in the code!
* Debugging on small dataset:
	* unit satureation: scale down initialization, normalize data
	* loss function going up and down: decrease learning rate 
	* If we don't reach good accuracy, something is wrong with the netrwork 

### Training is hard:
* Undefitting
* Overfitting
        * initialize hidden layers using unsupervised pretraining 
        * Use autoencoders to initialize the network layer by layer
* Greedy layer-wise pretraining 
        * Move layer by layer and train them as auto encoders and freeze the layers and and layers as you move on
* Dropout
        * Cripple the network by stochastically removing hidden units from the network with a probablity of 0.5 
        * At test time, we replace the masks by their expecatation (0.5 if the probability is 0.5)
        * For single hidden layer, dropout is equal to taking the geometric average of all neural netwrks with all possible binary masks.
        * Dropout results in slower training but improves the network performance  
* Batch normalization
        * More effective than dropout and helps with both overfitting and underfitting 
        * Data Normalization speeds up training 
        * In batch normalization, each unit's pre-actrivation is normalizaed.
        * during training, mean and stddev is computed for each minibatch 
        * backprop takes into account the normalization and at test time the global mean/stddev is used.
        * Introduces the scale and shift to move away for regulazation if necessary (gamma and beta are trained) as a learned linear transformation to adapt to non-linear activation function. 
        * Don't use batch normalization for softmax. 

