### What is Jahmm? ###

Jahmm is a general-purpose Java library implementing most algorithms related to Hidden Markov Models.  It has been originally written by Jean-Marc François.


### When learning the parameters of my HMM, I get a "Matrix is not positive defined" exception ###

The learning algorithm has tried to estimate the parameters of a multivariate Gaussian distribution, but has not been able to.  This most probably mean that the number of samples used is too small, or that the samples are linearly dependant.

For example, estimating the mean and variance of a mono-variate Gaussian distribution cannot be done using one sample; at least 2 samples are necessary.