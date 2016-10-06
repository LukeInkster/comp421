# Week 11 - Variational Autoencoders


## beyond vanilla RNNs: LSTM and GRU variants
`(Tuesday: Marcus)`
* Motivated by the vanishing/exploding gradients problem of vanilla RNNs, LSTM and GRU (and others) are architectures which are able to learn richer structure in time.
* we talked through the post that picks apart LTSM in particular on [Colah's blog](http://colah.github.io/posts/2015-08-Understanding-LSTMs)
* and we looked at the GRU architecture too

## Variational autoencoders
`(Wednesday: Luke and Harry)`
* we looked at a [Tutorial on Variational Autoencoders](http://arxiv.org/abs/1606.05908)
* [slides](variational_autoencoders.pdf)
* we will continue this discussion (and get to the the main paper [Autoencoding Variational Bayes](http://arxiv.org/abs/1606.05908)) next Tuesday.

## Catch-up: HMMs vs Kalman Filters vs Particle Filters
`(Friday: Marcus) NB. we're doing this now rather than a straight continuation of VAE stuff, as Max is away)'

We're talking about 3 varieties of "state space model". 
Each node in the underlying PGM has a single parent. As a consequence, no "explaining away" inference is required.

* HMMs
  * simple, useful, powerful
  * can view as a mixture model (plus conditional class, given previous class), OR as a Markov model (plus stochastic observations from). An HMM is both.
  * with appropriate transition probs, can make cycles, etc etc, any FSM structure in time that you like.
  * were s.o.t.a. for speech / OCR until mid-2000's. Wide use in bioinformatics
  * can predict, and 'retrodict'. (both via belief propagation, message passing == 'sum-product alg')
  * special case of BN, with parameter sharing (only learn 3 distributions)
  * can learn the parameters (EM: E is belief-prop to get distribution over hidden states, M is usual max likelihood learning).
  * can also find most likely trajectory (Viterbi algorithm == 'max-sum alg').
* Kalman filters
  * continuous variables form of HMMs
  * assumes Gaussian distributions
  * often not learned, although they could be - people typically 'wire in' transition and emission models
  * KF is the optimal tracker iff the system is linear and deviations are Gaussian
* particle filters
  * breaks restrictions of Kalman Filter: much more general
  * a population ('particles') acts as a proxy for the distribution over hidden state
  * particles move each time-step (== transition model)
  * particles re-weighted by the likelihood (== emission model)
  * that leads to tiny weights for most, so we re-sample
  * general, trivial to program. But you can't 'retrodict'. Less clear how to learn the model.
  * [someone's simple demo](https://salzis.wordpress.com/2015/05/25/particle-filters-with-python/)
  * widely used for target tracking, due to generality and simplicity.
* Comment / aside : tracking multiple targets is harder, and none of the above will do it. My veiw: essentially the new difficulty is due to the PGM now requiring "explaining away" style inference (interactions between the posterior over the multiple causes at play in the generative model). Ad hoc initiatives won't handle that properly, hence won't work for multiple targets.
