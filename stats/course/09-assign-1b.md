---
title: "Problem Set 1B: Bayesian Estimation"
description: Five problems on posteriors, MMSE, MAP, and LMMSE. After Kay I, chapters 10 through 12.
order: 9
section: module-1
---

# Problem Set 1B: Bayesian Estimation

Five problems on the Bayesian toolkit: posterior computation, MMSE, MAP,
LMMSE, and the discrete-prior case where the arithmetic is all Bayes.
Problems are paraphrased from Kay I, chapters 10–12: B1 after Kay I
§10.4, B2 after Kay I §10.7, B3 after Kay I §12.3, B4 after Kay I §10.2,
B5 after Kay I §10.8. All reference solutions are written fresh and
verified numerically.

General facts you may use without re-deriving:

- Gaussian–Gaussian conjugacy: with prior
  $\mathcal{N}(\mu_0, \sigma_0^2)$ and $n$ samples of known variance
  $\sigma^2$, the posterior is Gaussian with precision
  $1/\sigma_0^2 + n/\sigma^2$ and mean the precision-weighted average of
  $\mu_0$ and $\bar{x}$.
- Gamma–Poisson conjugacy: an $\mathrm{Exponential}(\beta)$ prior on a
  Poisson rate with total count $N$ gives a $\mathrm{Gamma}(N+1, \beta
  + T)$ posterior (shape/rate).
- Beta–Bernoulli conjugacy: a $\mathrm{Beta}(a_0, b_0)$ prior on a
  Bernoulli proportion with $k$ successes in $n$ trials gives a
  $\mathrm{Beta}(a_0+k,\ b_0+n-k)$ posterior.
- LMMSE from moments: $\hat{\theta} = \mu_\theta +
  \mathbf{C}_{\theta x}\mathbf{C}_{xx}^{-1}(\mathbf{x} - \boldsymbol\mu_x)$.

<Widget type="assignment" id="com.github.richbai90.stats.09-assign-1b.b1_gauss_posterior" />

<Widget type="assignment" id="com.github.richbai90.stats.09-assign-1b.b2_poisson_map" />

<Widget type="assignment" id="com.github.richbai90.stats.09-assign-1b.b3_lmmse" />

<Widget type="assignment" id="com.github.richbai90.stats.09-assign-1b.b4_beta_bernoulli" />

<Widget type="assignment" id="com.github.richbai90.stats.09-assign-1b.b5_discrete_prior" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.09-assign-1b.card_conjugacy" />

<Widget type="flashcard" id="com.github.richbai90.stats.09-assign-1b.card_mean_vs_mode" />
