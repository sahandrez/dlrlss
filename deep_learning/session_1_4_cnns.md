# Convolutional Neural Networks - Graham Taylor
Encoding domain knowledge is important in learning images.

## What drives CNN sucecesses:
* Compositionality/hierarchy
* Learned representations
* Gradient-descent based optimization
* Local receptive field topology 
* Translation equivariance 
* Translation invariance 

* A fully-connected layer is a waste of resource and spatial correlation is local.
* A locally-connected layer is good when the input images are regitstered (e.g. face recognition)

## Convolution
* linear operation
* weighted averaging operation in time and space
* Convolve 2D kernels with 2D images. 
* each hidden unit only recieves input from a local region of the image, its receptive field. 
* Padding to control the size of the output (no padding, half (same) padding, full padding)
	* zeros
	* replicate
	* symmetric 
* Convolutional layer: output feature map = Sum(input feature map * kernel)
* CNNs do weight sharing
* Pooling layer: Make the detection robust to its location in the image. Pool the filter response over a local region of the ap makes it robust to the exact spatial location of features -> shift invariance. The pooling is done on small regions so that the spatial properties of the image are not completely ignored.
	* max-pooling
	* avergae-pooling
	* l2-pooling
	* l2-pooling over features 
* Local contrast normalization: 
	* for every unit in the feature map, the mean and std of the neighborhood is used to normalize the feature maps. 
	* imporves invariance
	* imporves optimization
	* increases sparsity 
* In recent years, local contrast normalization is replaced by batch normalization.
	* A method of adaptive reparametrization, motivated by the difficulty of tarining very deep models.
	* Reduces the problem of coordinating updates.
* Batch normalization math:
	* compute batch mean 
	* compute batch variance
	* normalize pre-activation 
	* compute next layer's pre activation
* Caveat #1: Turning down or disabling regulations?
	* The test accuracy is not changed
	* But robustness is less forgiving 
* Caveat #2: Information loss and inabiity to maintain realative distances reduces adversarial as well as general robustness.

## Single Stage Conv Net
Convoluational layer -> Rectification + normalization -> pooling 

## Traditional Architecture
input -> stage 1 -> stage 2 -> stage 3 -> fully connected layers -> output 

## Training and Testing Conv Nets
* all layers are differentiatiable, thus we can use gradient descent methods 
* Optimization is not the real problem when:
	* dataset is large
	* units don't satureate 
* The real challenge is 
	* generalization 
	* scalibility 
## Profiles 
### AlexNet 
* First paper to populatrize DNNs in vision 
* Uses dropout regularization 

### Network-in-Network
* Replaces linear con layer with micro network architecture which is a nonlinear operation.
* Linear dimensionality reduction by convolving a NxNxD feature map with a 1x1xD kernel, resulting in NxNxD.

### Inception/GoogLeNet
* Inception module reduces the number of parameters in the network.
* Uses auxillary classifiers

### VGGNet 
* Showed that depth of the network of the net is a critial component.

### ResNet
* special skip connections and heavy use of batch normalization
* There is not fully connected layer at the end
* Residual model skips a layer and passes the output to the next layer.

### DenseNet
* Connects each layer to every other layer in a feed forward fashion.
* Strengthen feature propagation, alleviates vanishing gradients, reduces number of parameters 
* Combine features through concatenation rather than sum compared to ResNet.

### Squeeze-and-Excitation Networks 
* adaptive recalibration 
* Aggregate feature maps across spatial dimensions (squeez)
* Produce per channel modulation via FCN (excitation) 
* Apply the weights to rescale the feature maps 

### Different types of Convolutions
* Strided convolution 
	* All-convolutional nets: strides replace pooling 
* Dilated (Astrous)conolution 
	* inflate the kernel by inserting spaces between the kernel elements
	* Increases the receptive field size without increasing size of the kernel 
* Transposed convolutions
	* deconvolution, opposite to convolution.
	* decoder in VAEs or GANs

### Resource-constrained DL
* Network compression
* Network pruning
* Factoring weights
* Low precision learning 

### Applications of CNNs
* Stored as multi-dimensional arrays (tensors)
* Feature one or more axes for which ordering matters
* One axis, the channel is used to access different views of data
* Recently CNNs are used for graphs 






