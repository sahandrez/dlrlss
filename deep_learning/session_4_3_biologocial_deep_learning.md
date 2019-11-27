# Biological Deep Learning - Black Richards

## Why deep learning is not just for AI
At an abstact level, deep NNs opereate with some similar principals to the real brain, but there aresome important differences.

Conv nets were orriginally invented to mimic what is done in visual cortex with a hierarchical structure. But in brain there are many feedback connections. 

Deep learning models are a better fit to neocortical representations than models deceloped by neuroscienticsts.

There is a correlation between representations in human layers with deep layers of a conv net. 

The key feature of deep learnign is the ability to engaeg in end-to-end optimization in a many-layered networks. 

To do optimization we should do credit assignment to figure itu tthe contribition of each neuron -> back prop. None of these are identical to the synamptic changes in brain to date.

Things need to be adressed:
* Error term 
* Transpose of downstream 
* Seperate forward and backward 

The fact that brain does not have back prop, it means there are other bioloficaly possible credit assignment solutions.

## Error term 
The brain can def calculate erros but there is no evidence that synapses chanfe based on error term.Instread it is using spike-timening depentant plasticity. There was the "blue proejct" to use this learning methdo to train a neural net but it failed.

Euiqilibrium propahation method -> check the picture
They could get the same STP results experimentalist saw.

## Downstream Weight
In backprop, we assum that the hidden layer neurons have access to the error term multiplied by the transpose. But this is not true with brain -> lillicrap et. at 2016 -> feedback alighnment! 
feedback alignment is not effective always. 

An alternative is to train the feedback weights. Kolan an Polak 

## Seperate forward and backward pass
There is a mechanism in brain that enables neurons to communicate forward and backward simutlaneously. They have implemented the same thing on aritifical neural nets.
