## Preliminary Project Description: *Predictive Coding as an Algorithmic Implementation of RSA for Vagueness, with an Extension to Nouns*

**Motivation & Goal.**
[...]

**Core idea.**
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
**Feedback implementation.**
[...]
<br>
**Work package 1 — Replicate RSA results with feedback mechanism.**
[...]
<br>
**Methodological details (shared across WP1–2).**

* **Generative assumptions.** QUD-relative utility; cost ~ utterance length; ALT sets tailored to each domain (e.g., `{cup, bowl, ∅}`). Priors over degrees/features set from published norms or simple Gaussians/Beta distributions; uniform priors on free semantic variables unless data suggest otherwise.
* **Recognition dynamics.** PC message passing with precision scheduling; softmax likelihood for discrete `u`. Convergence diagnostics (free-energy decrease), and ablations varying `α`, costs, and ALT to test robustness and identifiability.
* **Evaluation.** [...] <br>

**Expected contributions.**
[...] <br>
**Feasibility & plan.**
[...] <br>
**Risks & mitigations.**

* *Discrete utterances in PC:* use a categorical/softmax node (or Gumbel-softmax for gradients).
* *Identifiability of `θ` vs prior scale:* anchor priors from norms; report sensitivity; include ALT/cost ablations.
* *Noun model complexity:* start with scalar/thresholded nouns; prototype/region as stretch target.

[1]:https://cocolab.stanford.edu/papers/LassiterGoodman2015-Synthese.pdf
