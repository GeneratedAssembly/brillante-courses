---
title: "Problem Set 5A: Information and Sampling"
description: Five problems on entropy and KL, the Occam factor, importance sampling, Metropolis–Hastings, and Gibbs sampling. After MacKay, chapters 1, 2, 28, and 29.
order: 44
section: module-5
---

# Problem Set 5A: Information and Sampling

Five problems on Lessons 37 through 39: pricing a mismatched code,
comparing two priors through the evidence, reweighting a proposal,
walking a Markov chain by hand, and cycling a Gibbs sampler. Work each
problem before opening its hint; submit; read the reference only
after the verdict. Problems are paraphrased from *Information Theory,
Inference, and Learning Algorithms* (MacKay, 2003): A1 after MacKay,
chapter 2 (entropy and mutual information), A2 after MacKay, chapter
28 (model comparison and Occam factors), A3 after MacKay, chapter
29 (Monte Carlo methods), A4 and A5 after MacKay, chapter 29 with
Barber, chapter 27 (Markov chain Monte Carlo). All reference solutions
are written fresh for this course and verified numerically.

Conventions: entropies and divergences are in nats unless the problem
says bits; $\mathrm{KL}(p \,\|\, q) = \sum_x p(x)\ln(p(x)/q(x))$ for
discrete distributions with $\mathrm{KL} = 0$ iff $p = q$; a proposal
distribution is $q$, the target is $p$; importance weights are
$w_i = p(z_i)/q(z_i)$ up to normalization; Metropolis–Hastings
acceptance is $\min\left(1,\, \tilde p(z')\,q(z \mid z') /
\tilde p(z)\,q(z' \mid z)\right)$ with $\tilde p$ the unnormalized
target; a full Gibbs sweep updates every block once.

General facts you may use without re-deriving:

- The evidence factorizes as $p(D \mid M) \approx
  \mathcal{L}_{\max}\,(\text{posterior width}) / (\text{prior width})$
  for a unimodal likelihood.
- The importance-sampling effective sample size is
  $\mathrm{ESS} = \left(\sum_i w_i\right)^2 / \sum_i w_i^2$ on
  normalized weights, and the self-normalized estimator is
  $\hat\mu = \sum_i \bar w_i f(z_i)$ with $\bar w_i$ normalized.
- For a two-state chain with transition matrix $\mathbf{P}$, the
  stationary distribution satisfies $\boldsymbol\pi\mathbf{P} =
  \boldsymbol\pi$, $\sum_i \pi_i = 1$.
- Gibbs sampling draws each block from its exact conditional given the
  current values of the others; every draw is accepted.

<Widget type="assignment" id="com.github.richbai90.stats.44-assign-5a.a1_kl" />

<Widget type="assignment" id="com.github.richbai90.stats.44-assign-5a.a2_occam" />

<Widget type="assignment" id="com.github.richbai90.stats.44-assign-5a.a3_importance" />

<Widget type="assignment" id="com.github.richbai90.stats.44-assign-5a.a4_metro" />

<Widget type="assignment" id="com.github.richbai90.stats.44-assign-5a.a5_gibbs" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.44-assign-5a.card_surprise" />

<Widget type="flashcard" id="com.github.richbai90.stats.44-assign-5a.card_balance" />
