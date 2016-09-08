# Week 7 - still figuring out what best to do this week.


## The Bayesian Way 
`(Tuesday, and then Wednesday too: Marcus)`

* Bayes theorem updates prior into posterior
* aside: have a look at [[https://en.wikipedia.org/wiki/Bayesian_probability#Justification_of_Bayesian_probabilities]], for why we're taking it as read that probability theory is the language of inference
* we're usually interested in the posterior distribution over an unknown or "latent" variable
* Bayes theorem tells us we need to first provide a prior distribution over it - it's obligatory
* we looked at the example of a single coin of unknown bentness
* aside: intro / reminder of conventions in denoting PGMs (probabilistic graphical models) - unshaded nodes are "hidden" variables, shaded are "visible" variables, black balls are "assumed" variables. Think of _directed_ links as causal connections. That's probably enough to go on for now.
* we used a "flat" prior
* the (one) hidden variable is %$b$%, the true bentness of the coin, where "bentness" simply means its true probability of generating a head on any one throw. We don't know this - the variable is "hidden", also called "latent".
* the visible node is the data. It's in a "plate", meaning there are _really_ several such nodes, one for every datum (coin toss), but drawing them all is tedious so we just draw one and use the rectangle instead. The "full" PGM would have a link from the one hidden unit to each of the individual datum units. There would be no connections between those datum units: this is the same as saying the data is assumed to be generated "i.i.d.".
* with i.i.d. data, the new posterior can be used as the prior for subsequent events (or you can group all the events together and assess the total likelihood - the two are equivalent)
* using the max likelihood value is prone to over-fitting if there's not enough data
* using the MAP (maximum a posteriori) value is better, but only if you've got a prior that's "informative" - the flat one assumes nothing at all, and hence doesn't alleviate over-fitting.
* but _really_ both these approaches are wrong, since they involve (premature) maximization!
* we looked at how a true-blue Bayesian makes predictions without doing any such maximization.


## Third lect
`(Friday: Marcus)`
* stuff

