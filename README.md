# information-entropy
Information theory notes focused on entropy

### Thermodynamics
In thermodynamics, entropy is a measure of a system's "disorder", or the amount of energy unavailable to do work (*ΔG=ΔH−TΔS*). This concept of disorder is intuitive to a chemist, who understands that molecules tend towards states with greater degrees of conformational freedom. When designing a drug molecule, for example, the entropic cost of stabilizing the disordered sidechains of a protein binding site must be overcome by other favorable molecular interactions with the drug.

### Information Theory
While the concept of molecular disorder helps to explain entropy to a chemist, it does not generalize well to a statistical understanding of entropy. Instead of this vague concept of "disorder", let's look at the formula which is the weighted sum of *ln(p<sub>i</sub>)* for all the microstates *i* with probabilities *p<sub>i</sub>* in an ensemble:

![entropy_thermodynamics](entropy_thermodynamics.svg)

In the case of equiprobable microstates, this formula collapses into the famous and much more simple form:

![entropy_boltzmann](entropy_boltzmann.svg)

Here, *k*<sub>B</sub> is the Boltzmann constant, and Ω is the number of microstates. What we can learn from this formula is that the number of microstates (conformations) scales exponentially with the energy of the system.

Turning to the formal definition of information entropy, we are presented with essentially the same formula, which, arguably, can be considered a more general form of the thermodynamics version (ignoring the Boltzmann constant):

![entropy_information](entropy_information.svg)

Common numbers for b are 2 (bits) or Euler's number *e* (thermodynamics).

- #### Definition of information
  To model the world as Shannon did, we must think of all processes as messages attempting to communicate information to a receiver. The information content of a message is expressed in bits as *ln(p<sub>i</sub>)*. The rarer the probability of the event, the greater the information such an event would convey.
 
- #### Information Entropy
  Information entropy is the *expected* information conveyed across all states, thus leading to the general formula -Σ*p<sub>i</sub>log(p<sub>i</sub>)*. Here's where it all ties back together with the thermodynamics understanding of entropy. Consider a family of peptides of the same length, where the amino acids expected to appear at each position are known from a sequence alignment analysis. If only alanine ever appears at position 1, no new information can be communicated about its state, and therefore the information content of any message, the "disorder", as well as the entropy at this position, is zero. On the other extreme, if all amino acids are equiprobable at this position, the information entropy is maximum (as is the disorder). On a larger scale, the thermodynamic entropy is maximum when all possible states of the universe are equiprobable ("the end of the universe" where there is no longer any order to the universe). Both the information and thermodynamics versions of entropy quantify the uncertainty of the state of the system.

- #### Cross Entropy
  What if we want to compare the similarity/divergence between two probability distributions? Cross entropy is the expected number of bits required to convey a message about estimated probability distribution *q* given a coding scheme optimized for the true distribution *p*. Formulaically, this is calculated as the sum of all *ln(q<sub>i</sub>)* weighted by the true distribution *p<sub>i</sub>*:
  
  ![cross_entropy](cross_entropy.svg)
  
- #### KL Divergence
  The cross entropy is always greater than or equal to the entropy of the true distribution, and this difference is the Kullback–Leibler divergence. Specifically, it measures the uncertainty introduced from trying to communicate distribution *q* using a coding scheme optimized for the true distribution *p*.
