_Note: remember to explore any ipython notebooks in this directory._


# Week 8 - Gaussian Processes and MCMC

NB: both of these could be called Bayesian machine learning methods. There is also an interesting connection between them: it has been shown that Bayesian neural networks revert to being essentially Gaussian processes as the number of hidden units tends to infinity. Notice that to the usual "learning is optimization" way of thinking, having so many free parameters would be a disaster, but the Bayesian story is that _provided you integrate over the uncertainty_ you don't get over-fitting: instead, in this case you get a Gaussian process!

## Gaussian processes 
`(Tuesday, and Wednesday: Marcus)`
See [slides](Gaussian_Process_slides.pdf) or as [handouts](Gaussian_Process_handouts.pdf)


## Metropolis (MCMC) via an example: Bayesian neural nets.
'(Friday: Marcus)'
See [slides](Metropolis_slides.pdf) or as [handouts](Metropolis_handouts.pdf)
* beware the copy-and-paste typo in the figures at the end: the number of hidden units can be detected by looking at the curves (e.g. if they're simple sigmoids then there's 1 hidden, if the look like two sigmoids added together then... etc.)
