# Recurrent Neural Nets - Yoshua Bengio
* Unfolding the graph tells us how to back prop through time.

* Selectively summarize an input sequence in a fixed size state vector via a recursive update: s_t = F_theta(s_{t-1}, x_t)
* Generalizable to new length of data

* Lifting & parameter sharing:
	*  Seperate the small parameter 
* Generative RNNs 
	* an rnn can represent a fulluy connected direceted generative model: evey variable predicted from all previous ones. P(x) = P(x1, x2, ..., xT), Lt = -log(P(xt|xt-1, xt-2, ..., x1))
	* Dotted arrow: we can use the models to generate new sequences (check the picture)
	* o_t = vector of probabilites for all possible values 
	* We are not assuming the distribution is markovian 

* Conditional distributions
	* seq to vec
	* seq to seq of the same length
	* vec to seq 
	* seq to seq : two rnns, one to read the input and another generative rnn -> machine translation 
* Maximum likelhood: teacher forcing
	* during traingn, past y in input is from trainnig data
	* at generation time, past y i n input is generated 
	* mismatch can cause compounding error -> driving example 
* Ideas to reduce train/genrate
* Increasing the expressive power of rnns with more depth 
* bidirectional 
* multiplicative interactions
* multiscale or hierechical rnns 
	* gradients can propagate over longer spans through slow time scale paths 
	* intorudce a network architecture that update the states of its hidden layers with different speeds in order to capture multiscale representation of sequences
* Some subspace of the state can store
* Small change -> no change or large change    
* Why vanishing gradient hurts learning?
	* weight sharing across time so the problem is worse than in deep nets 
	* long term dependencies get a weight that is exponentially smaller in T compared to short term dependencies 
* gradient explosion:
	* renormolize gradient when it is larger than a threshold
## RNN trickes 
Some tricks for training rnns 
* delays (skip connections) and multiple time scales 
* Hierarchichal rnns 
* Fighting the vanishing gradient LSTM and GRU 
	* using gates 
* Keeping the eigen values near 1 
	* unitary rnns 
	* parametrize linear operator as product of unitary blocks
	* not rich enough parametrization and limited to normal matrices

## Non parametric memory escapes the vanishing gradient curse
* memory loss is that two memories are mapped to one spot 
* one solution is to go nonparametric -> infinite memory 
* two states: 
	* micro state: rnn
	* macro state: need attention mechanisms to read from the memory and possibly write into it
* Attention based nets
	* able to look back and get the information
* graph based neural nets 

* from memory to system 2:
* large memory networks 
* multi-head attention
* self attention and transformerers 

