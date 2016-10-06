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
`(Friday: Marcus)`
* (we're doing this now rather than a straight continuation of VAE stuff, as Max is away)
* HMMs
  * simple, useful, powerful
  * were s.o.t.a. for speech / OCR until mid-2000's. Wide use in bioinformatics
  * can predict, and 'retrodict'. (both via belief propagation, message passing == 'sum-product alg')
  * can learn the parameters (EM: E is belief-prop).
  * can also find most likely trajectory (Viterbi algorithm == 'max-sum alg').
  * special case of BN, with parameter sharing (only learn 3 distributions)
* Kalman filters
  * continuous variables form of HMMs
  * assumes Gaussian distributions (is optimal tracker if system is linear and deviations are Gaussian)
  * often not learned - people 'wire in' transition and emission models
* particle filters
  * breaks restrictions of Kalman Filter: much more general
  * a population ('particles') acts as a proxy for the distribution over hidden state
  * particles move each time-step (== transition model)
  * particles re-weighted by the likelihood (== emission model)
  * that leads to tiny weights for most, so we re-sample
  * general, trivial to program. But you can't 'retrodict'. Less clear how to learn the model.
  * [someone's simple demo](https://salzis.wordpress.com/2015/05/25/particle-filters-with-python/)
* if time: why multiple targets is hard!
