# Introduction #

Jahmm provide an implementation of various algorithms related to HMMs.


# Details #


## Basic Hidden Markov Model-related algorithms ##

  * Forward-Backward (estimation of the probability of an observation sequence given a HMM) with scaling (meaning that this computation won't generate underflows with long sequences);
  * Viterbi (finds the most likely state sequence that match a given observation sequence given a HMM);
  * An observation sequence generator matching a HMM.


## Hidden Markov Model learning algorithms ##

The learning is based on a set of observation sequences (not only one).

  * K-Means learning;
  * Baum-Welch learning with scaling (meaning that a learning based on long observations sequences don't generate underflows).


## Other Hidden Markov Model-related algoritms ##

  * 'Kullback-Leibler'-like estimation of the distance between two HMMs.


## Observation distributions ##

  * Distributions of observations drawn from a finite set (e.g. bounded integers);
  * Gaussian distribution;
  * Gaussian mixture distribution;
  * Multi-variate Gaussian distribution.


## Pseudo-random generator ##

  * A Gaussian number generator;
  * A Gaussian mixture number generator;
  * A multi-variate Gaussian-distributed number generator based on the Cholesky decomposition of the covariance matrix;
  * An exponentially-distributed number generator;
  * A Poisson-distributed number generator.


## Other ##

  * K-means clustering (using the standard algorithm, an optimized version of Loyd's classical version).