## Preliminary Project Description*

**RSA**
Lassiter & Goodman's "Adjectival vagueness in a Bayesian model of interpretation" (2015) proposes a formal model of how the free threshold in adjectives are determined in-context, which they named the Rational Speech Act (RSA). This model adopts a three-step recursive bayesian inference approach: the pragmatic listener L1 infers world state (A) from the utterance (u) of the speaker S1, who infers the utterance from a supposed literal listener(L0)'s world state, who infers the world state given the literal meaning of u is true. The function performed by each agent is as follows: <br>
$$
P_{L_0}(A \mid u, V) \;=\; P_{L_0}\!\big(A \mid \llbracket u \rrbracket_V = 1\big)
$$
<br>
$$
P_{S_1}(u \mid A, V) \;\propto\; 
\exp\!\Big(\alpha \big[\ln P_{L_0}(A \mid u, V) - C(u)\big]\Big)
$$
<br>
$$
P_{L_1}(A, V \mid u) \;\propto\; P_{S_1}(u \mid A, V)\,P_{L_1}(A)\,P_{L_1}(V)
$$
<br>
(!need to figure out LaTex embedding)

**Motivation & Goal.**

RSA is known to yield inaccurate results in scalar implicatures and absolute adjectives. In the case of scalar implicature, it is argued that listeners are insensitive to prior manipulations [cite], but this is not necessarily the case. Taking the example from [cite], if we present subjects with the scenario: Someone threw 10 blocks of marble in the water; John, who witnessed the event, told you that 'some marbles sank.', then RSA supposedly predicts that the interpretation is most likely 'all marbles sank'. This is not what RSA predicts. Note that in S1, the KL-divergence this interpretation yields tends to 0. Therefore, the probability of this interpretation at L1 would also tend to zero. In other words, if our world-state prior predicts that 100% of chance all marbles would sink, then an interpretation that exactly matches this prior would yield no reduction of entropy whatsoever, as there is no room for reduction in the first place. RSA did not address the question of what do listeners do when the only interpretation that follows from a highly concentrated world-state prior yields no informativity (and how do we determine the threshold of 'no informativity').   
 
**Feedback implementation.**

Any computational model would need to satisfy the following constraints to be considered biologically plausible:<br>
1. Local computation: A neuron performs computations only on the basis of the activity of its input neurons and synaptic weights associated with these inputs (rather than information encoded in other parts of the circuit). <br>
2. Local plasticity: Synaptic plasticity is only based on the activity of pre-synaptic and post-synaptic neurons.<br>
[cite]

**Work package 1 — Replicate RSA results with feedback mechanism.**
[...]

**Methodological details (shared across WP1–2).**

* **Generative assumptions.** QUD-relative utility; cost ~ utterance length; ALT sets tailored to each domain (e.g., `{cup, bowl, ∅}`). Priors over degrees/features set from published norms or simple Gaussians/Beta distributions; uniform priors on free semantic variables unless data suggest otherwise.
* **Recognition dynamics.** PC message passing with precision scheduling; softmax likelihood for discrete `u`. Convergence diagnostics (free-energy decrease), and ablations varying `α`, costs, and ALT to test robustness and identifiability.
* **Evaluation.** [...] <br>

**Expected contributions.**
[...] 

**Feasibility & plan.**
[...] 

**Risks & mitigations.**

* *Discrete utterances in PC:* use a categorical/softmax node (or Gumbel-softmax for gradients).
* *Identifiability of `θ` vs prior scale:* anchor priors from norms; report sensitivity; include ALT/cost ablations.
* *Noun model complexity:* start with scalar/thresholded nouns; prototype/region as stretch target.

[1]:https://cocolab.stanford.edu/papers/LassiterGoodman2015-Synthese.pdf
