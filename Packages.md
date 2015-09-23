The library has been divided in several Java _packages_, explained below:

| **Package name** | **Description** |
|:-----------------|:----------------|
| `be.ac.ulg.montefiore.run.jahmm` 	| The main package, containing the definitions of HMMs, observations and observation probability distribution functions. It also holds the implementation of the Viterbi and Forward-Backward algorithms.|
| `be.ac.ulg.montefiore.run.jahmm.learn` | This package holds the learning algorithms (algorithms that fit HMMs to observation sequences). |
| `be.ac.ulg.montefiore.run.jahmm.io` |	This package converts data files to Java objects.|
| `be.ac.ulg.montefiore.run.jahmm.toolbox` |	Various tools related to HMMs. For example, a distance measure between HMMs based on the Kullback-Leibler distance is given here.|
| `be.ac.ulg.montefiore.run.jahmm.apps` |	Applications based on Jahmm. It holds Jahmm's command-line interface.|
| `be.ac.ulg.montefiore.run.distributions` | 	Implementation of various pseudo-random distributions (including multivariate gaussian distributions and monovariate Gaussian mixtures).|