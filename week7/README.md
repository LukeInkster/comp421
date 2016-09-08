# Week 7 - The Bayesian Way

## The Bayesian Way 
`(Tuesday, and Wednesday too, and then a discussion on Friday: Marcus)`

See [slides](big-bayes-slides.pdf) or the 4-slides-per-page [handouts](big-bayes-handouts.pdf)

Your bullet-point summary might go something like this:
* Bayes theorem updates prior into posterior
* probability theory is [the language of inference](https://en.wikipedia.org/wiki/Bayesian_probability#Justification_of_Bayesian_probabilities)
* we're usually interested in the posterior distribution over an unknown or "latent" variable
* Bayes theorem tells us we need to first provide a prior distribution over it, even before seeing any data - it's obligatory! Seems odd, but then it also seems obvious to incorporate background knowledge / assumptions.
* we looked at the example of comparing two coins of known bentness
* then we looked at the example of a single coin of unknown bentness
* aside: intro / reminder of conventions in denoting PGMs (probabilistic graphical models) - unshaded nodes are "hidden" variables, shaded are "visible" variables, black balls are "assumed" variables. Think of _directed_ links as causal connections. That's probably enough to go on for now.
* we used a "flat" prior
* the (one) hidden variable is the true bentness of the coin, where "bentness" simply means its true probability of generating a head on any one throw. We don't know this - the variable is "hidden", also called "latent".
* the visible node is the data. It's in a "plate", meaning there are _really_ several such nodes, one for every datum (coin toss), but drawing them all is tedious so we just draw one and use the rectangle instead. The "full" PGM would have a link from the one hidden unit to each of the individual datum units. There would be no connections between those datum units: this is the same as saying the data is assumed to be generated "i.i.d.".
* with i.i.d. data, the new posterior can be used as the prior for subsequent events (or you can group all the events together and assess the total likelihood - the two are equivalent)
* using the max likelihood value is prone to over-fitting if there's not enough data
* using the MAP (maximum a posteriori) value is better, but only if you've got a prior that's "informative" - the flat one assumes nothing at all, and hence doesn't alleviate over-fitting.
* but _really_ both these approaches are wrong, since they involve (premature) maximization!
* we looked at how a true-blue Bayesian makes predictions without doing any such maximization.

## Third session: discussion and extension
* do we understand optimization vs inference? Review log loss as likelihood, and reconsider regularisation as the effect of a prior. EG: NN with weight decay == MAP inference with a Gaussian prior on weights.
* the fully Bayesian prediction doesn't overfit: overfitting is a consequence of optimization, not inference
* how a Bayesian chooses between two different models (Bayes factor)
* why Bayes embodies Ockham's razor
* so what's the problem? That integration. Maybe this is a lecture next week then:
   * exact cases: Dirichlet-multinomial, Gaussian process...
   * integration by sampling: MCMC (Metropolis and Gibbs).
