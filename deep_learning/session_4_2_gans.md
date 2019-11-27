# Generative Models - Ka Li 
* deterministic models 
* probabilistic models
	* goal: map inout x to a distribution
	* model p(Y|x)
* Implicit prob model

## Learning probabilistic models
* maximum likeliood estimateion MLE 
	* theta(mle) = argmax p(y1, ..., yn)
	* maximize the likeligood function 
	* log likelighood function = -log likelihood

## KL Divergence
* measure the difference between two distribuions
	* non negatvitiy
	* zero if and only if equal 
	* asymmetry
* Meaning 
	* We draw n iid samples from a adiscrete distrit Q and consider the distu of freq of each value
	* DKL(P||Q) tells us how exponentialy unlikely it is for this distribution to be similar to P 
	* this intrep is justified by a speical case -> see the photo
* connection to maximum likelihood
	* max likeligood is equavalent to miniming the kl divergence 

## Variational Autoencoders
see the hand written notes.



	  

