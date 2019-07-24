# Deep Learning 2 - Hugo Larochelle 

## Adversarial Examples 
* Deep nets have many non-convex saddle points 
* The saddle points need to be identified and attacked: "Identifying and attacking the saddle point problem in high dimensional .. NIPS 2014 - Benjio"
* if a dataset is created by labeling using a N-hidden units neural net with random weight. Even though there is a network existing that creates that dataset, it is impossible to train another net to reach the perfect performance. But we are able if we use a larger network.
* "Measuring the intrinsic Dimenstion of objectve landscapes"
* "The lottery ticket hypothesis: finding sparse, trainable networks"
* "Flat Minima - Schmidhuber"
* "Understanding deep learning requires rethinking generalization"
	* If labels are random, generalization is impossible
* "On large batch training for deep learning generalization .. "
* "Reconciling modern machine learning and the bias-variance trade-off"
	* under parametruzed and over-parametrized 
	* There is a threshold between under-param and over-param where the risk is maximized!  
* Knowledge distillation "Distilling the knowledge in a neural network"
	* you can disill a network to a smaller one that performs almost the same, but you can't train that small net from scratch 
