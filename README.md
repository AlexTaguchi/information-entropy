# information-entropy
Information theory notes focused on entropy

### Thermodynamics
In thermodynamics, entropy can be described as the amount of "disorder" in a system, or the amount of energy unavailable to do work (*ΔG=ΔH−TΔS*). This concept of disorder is intuitive to a chemist, who understands that molecules tend towards states with greater degrees of conformational freedom. When designing a drug molecule, for example, the entropic cost of stabilizing the disordered sidechains of a protein binding site must be overcome by other favorable molecular interactions with the drug.

### Information Theory
While the concept of molecular disorder helps to explain entropy in thermodynamics, it does not generalize well to a statistical understanding of entropy. Instead of "disorder", let's recall the thermodynamics definition of entropy as the weighted sum of *ln(p<sub>i</sub>)* for all the microstates *i* with probabilities *p<sub>i</sub>* in an ensemble:

![entropy_thermodynamics](entropy_thermodynamics.svg)

Here, entropy expresses the number of microstates for a given macrostate in energy units. The number of microstates (particles) scales exponentially with the energy of the system, hence the logarithm.

Turning to the formal definition of information entropy, we are presented with essentially the same formula, which, arguably, can be considered a more general form of the thermodynamics version (ignoring the Boltzmann constant):

![entropy_information](entropy_information.svg)

Common numbers for b are 2 (bits) or Euler's number *e* (thermodynamics).

- #### Information Content
  To model the world as Shannon did, we must think of all processes as messages attempting to communicate information content to a receiver. The information content of a message is expressed in bits:
  
  ![information_content](information_content.svg)
  
  The rarer the probability of the event being specified, the greater the amount of information that is conveyed.
 
- #### Information Entropy
  Information entropy is the *expected* amount of information to be transmitted for all of the states in question, as shown above:
  
  ![entropy_information](entropy_information.svg)
  
  Here's where it all ties back together with the thermodynamics definition of entropy. Consider a family of peptides of the same length, where the amino acids expected to appear at each position are known from a sequence alignment analysis. If only alanine ever appears at position 1, no new information can be communicated about its state, and therefore both the information content of any message, as well as the entropy, is zero. On the other extreme, if all amino acids are equiprobable at this position, the information entropy is maximum. Analogously, the thermodynamic entropy is maximum when all possible microstates are equiprobable in the macrostate (the end of the universe). The greater the uncertainty of the system, the greater the information content expected to be obtained from any message/measurement.
