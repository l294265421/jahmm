## Introduction ##

This site describes Jahmm (pronounced "jam"), a Java implementation of Hidden Markov Model (HMM) related algorithms. It's been designed to be easy to use (e.g. simple things are simple to program) and general purpose. As it is licensed under the new BSD license; its source code is thus freely available.

This library is reasonably efficient, meaning that the complexity of the implementation of the algorithms involved is that given by the theory. However, when a choice must be made between code readability and efficiency, readability has been chosen. It is thus ideal in research (because algorithms can easily be modified) and as an academic tool (students can quickly get interesting results).

[Various Algorithms](Algorithms.md) are included in the latest version.

The library also provides a [command-line interface](CLI.md).


## Examples ##

This [Example](Example.md) shows how to program the library to build a HMM, to generate observation sequences, to use a learning algorithm and to read a data file.


## Download ##


See the download section to get access to the `.jar` files and sources of the library.


## Documentation ##

You will find an answer to the most frequent questions in the [FAQ](FAQ.md) section.
A short description of the Java packages is given in the [Packages](Packages.md) page.

See the _download_ section to get access to the library user guide, _Javadoc_, and source code.

The library documentation is not intended to be a HMM tutorial. Please refer to the following papers/books for more information about HMMs:

  * Rabiner, Juang, An introduction to Hidden Markov Models, IEEE ASSP Mag., pp 4-16, June 1986
  * Juang, Rabiner, The segmental k-means algorithm for estimating the parameters of hidden Markov Models, IEEE Trans. ASSP, vol. 38, no. 9, pp. 1639-1641, Sept. 1990.
  * Juang, Rabiner, A Probabilistic distance measure for HMMs, AT&T Technical Journal, vol. 64, no. 2, pp. 391-408, Feb. 1985.
  * Juang, Rabiner, Fundamentals of speech recognition, Prentice All, AT&T, 1993.