## Presentation ##

Instead of writing a Java program to use the library, it can be interfaced via a command-line interface (CLI).

Most algorithms can be launched this way, including creating HMMs (which are written to a human-readable file), learning the parameters of a HMM given observation sequences and printing a HMM.

An exhaustive list of the available options are described in the user guide.



## Example ##

We re-write an example covered on another page using the command-line interface. In short, the idea is to:
  * Create a reference HMM.
  * Generate sequences of observation using this model.
  * Create another HMM which is a rough approximation of the reference.
  * Improve the approximation using the observation sequences so that it approaches the reference.
  * Monitor the distance between the approximation and the reference as the former is improved.



## Creating a HMM ##

We first create a file that represents our reference HMM. It should look like the following.
```
Hmm v1.0

NbStates 2

State
Pi 0.95
A 0.95 0.05
IntegerOPDF [0.95 0.05 ]

State
Pi 0.05
A 0.10 0.90
IntegerOPDF [0.20 0.80 ]
```

The created HMM has 2 states and operates over integer observations. The allowed observations are 0 and 1. In the first state, the probability of 0 equals 0.95 and the probability of 1 equals 0.05. This file can be read by the CLI interface.

To verify that the file does not contain any syntax error, we print a description of the HMM using the interface:

<tt>java be.ac.ulg.montefiore.run.jahmm.apps.cli.Cli print -i test.hmm</tt>

This supposes that the classpath of java can find the class Cli and that the file is named <tt>test.hmm</tt>. In the following, we will suppose that jahmm-cli has be aliased to <tt>java be.ac.ulg.montefiore.run.jahmm.apps.cli.Cli</tt>.



## Generating observation sequences ##

If the file test.hmm contains a HMM, the following command generates a file test.seq which contains sequences that match the HMM.

<tt>jahmm-cli generate -opdf integer -r 2 -i test.hmm -os test.seq</tt>

The <tt>-opdf integer -r 2</tt> parameters describe the distributions associated with the states of the input HMM. The <tt>-r 2</tt> parameter means that 2 different observations are allowed (0 and 1).



## HMM parameters learning ##

The Baum-Welch learning process takes a HMM file (here <tt>test.hmm</tt>) and a file containing observation sequences (<tt>test.seq</tt>) to create a new HMM (<tt>learn.hmm</tt>). The parameters of the created HMM match the sequences better than those of <tt>test.hmm</tt>. The Baum-Welch algorithm is iterative; the number of iterations can be modified using the <tt>-ni</tt> switch.

<tt>jahmm-cli learn-bw -opdf integer -r 2 -i test.hmm -o learn.hmm -is test.seq</tt>



## Computing the distance between two HMMs ##

The following command computes the Kullback-Leibler distance between HMMs described by the files <tt>test1.hmm</tt> and <tt>test2.hmm</tt>.

<tt>jahmm-cli distance-kl -opdf integer -r 2 -i test1.hmm -ikl test2.hmm</tt>


## Scripting ##

Instead of launching the CLI 'by hand', one usually finds it more convenient to put all the commands in a script. Under Unix, the example above could be written in a short bash shell script such as this one:
http://jahmm.googlecode.com/svn/wiki/assets/cli/simpleExample.sh

This script is easily readable and could be converted to other scripting languages.