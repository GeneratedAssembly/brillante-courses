---
title: "Problem Set 4B: Bounds, Fields, and Codes"
description: Five problems on a three-node Markov field, the Gaussian ELBO gap, PPCA from an eigenspectrum, an analytic VAE bound, and topic unmixing against a Dirichlet prior. After Barber, chapters 4 and 11, and Bishop, chapter 12.
order: 36
section: module-4
---

# Problem Set 4B: Bounds, Fields, and Codes

Five problems on Lessons 29, 31, 33, and the synthesis of
[Lesson 34](/course/stats/unification): computing with an undirected
model, pricing the variational gap in a case with a closed form,
reading a factor model off an eigenspectrum, evaluating the VAE bound
analytically, and unmixing topics with a conjugate prior. Work each
problem before opening its hint; submit; read the reference only
after the verdict. Problems are paraphrased from *Bayesian Reasoning
and Machine Learning* (Barber, 2012) and *Pattern Recognition and
Machine Learning* (Bishop, 2006): B1 after Barber, chapter 4 (Markov
random fields), B2 after Barber, chapter 11 (variational inference),
B3 after Bishop, section 12.1 (probabilistic PCA), B4 after Kingma and
Welling, section 2.5 with Barber, chapter 11 (the variational bound for
a Gaussian decoder), B5 after Barber, chapter 13 (latent Dirichlet
allocation) with the unmixing lens of Lesson 24. All reference
solutions are written fresh for this course and verified numerically.

Conventions: Gaussian densities carry unit variance unless stated;
$\mathrm{KL}(q \,\|\, p)$ is the Kullback–Leibler divergence
$\int q \ln(q/p)$; the ELBO of latent $z$ and observation $x$ is
$\mathcal{L} = \mathbb{E}_q[\ln p(x, z)] - \mathbb{E}_q[\ln q(z)]$;
the identity $\ln p(x) = \mathcal{L} + \mathrm{KL}(q \,\|\,
p(z \mid x))$ holds for any normalized $q$.

General facts you may use without re-deriving:

- For Gaussians, $\mathrm{KL}(\mathcal{N}(m_1, v_1) \,\|\,
  \mathcal{N}(m_0, v_0)) = \tfrac{1}{2}\left[\ln(v_0/v_1) +
  (v_1 + (m_1 - m_0)^2)/v_0 - 1\right]$.
- The entropy of $\mathcal{N}(m, v)$ is
  $\tfrac{1}{2}\ln(2\pi e\, v)$.
- Gaussian–Gaussian conjugacy:
  $p(z) = \mathcal{N}(0, 1)$, $p(x \mid z) = \mathcal{N}(z, s^2)$,
  $x$ observed, gives posterior variance
  $v = s^2/(s^2 + 1)$ and posterior mean $v x$.
- Probabilistic PCA with $q$ retained components: $\sigma^2_{\mathrm{ML}}$
  is the mean of the $d - q$ discarded eigenvalues, and column $i$ of
  $\mathbf{W}$ aligns with eigenvector $i$, with
  $\|\mathbf{w}_i\| = \sqrt{\lambda_i - \sigma^2_{\mathrm{ML}}}$.

<Widget type="assignment" id="com.github.richbai90.stats.36-assign-4b.b1_mrf" />

<Widget type="assignment" id="com.github.richbai90.stats.36-assign-4b.b2_elbo_gap" />

<Widget type="assignment" id="com.github.richbai90.stats.36-assign-4b.b3_ppca" />

<Widget type="assignment" id="com.github.richbai90.stats.36-assign-4b.b4_vae" />

<Widget type="assignment" id="com.github.richbai90.stats.36-assign-4b.b5_topics" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.36-assign-4b.card_partition" />

<Widget type="flashcard" id="com.github.richbai90.stats.36-assign-4b.card_gap" />
