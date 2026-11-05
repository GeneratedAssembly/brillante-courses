---
title: Continuous Latents
description: Factor analysis and probabilistic PCA, the nonlinear decoder, the variational autoencoder objective, and reparameterization. After Bishop, chapter 12, Barber, chapter 11, and Kingma and Welling, 2013.
order: 33
section: module-4
---

# Continuous Latents

The mixture's latent was a switch; factor analysis's latent is a vector,
a low-dimensional code that explains a high-dimensional observation
through a noisy linear map. Probabilistic PCA is the Gaussian special
case, and its maximum likelihood solution closes the loop with the SVD of
[Lesson 19](/course/stats/ill-posedness). Replace the linear decoder with
a neural network and exact inference collapses; the variational
autoencoder restores tractability with the bound of
[Lesson 31](/course/stats/em-elbo) and one clever substitution. After
Bishop, chapter 12, Barber, chapter 11, and Kingma and Welling, 2013.

## Factor analysis and PPCA

<Widget type="math" id="com.github.richbai90.stats.33-continuous-latents.ppca" />

With Gaussian latents and Gaussian noise the marginal is Gaussian, and
its covariance $\mathbf{W}\mathbf{W}^{\mathsf T} + \sigma^2\mathbf{I}$
has low rank plus a floor. Maximum likelihood aligns the latent subspace
with the top eigenvectors of the sample covariance, with
$\sigma^2$ absorbing the average of the discarded eigenvalues; the
spectrum itself tells you how much variance is noise floor. The estimator lives in
the same eigensystem the pseudoinverse of
[Problem Set 3A](/course/stats/assign-3a) used; this is
[Lesson 21](/course/stats/tikhonov-nnls) told from the generative side.

<Widget type="quiz" id="com.github.richbai90.stats.33-continuous-latents.quiz_ppca" />

## The nonlinear wall

Make the decoder nonlinear and the marginal (the integral of
$p(\mathbf{x} \mid \mathbf{z})$ over all $\mathbf{z}$) has no closed
form. Neither the likelihood nor the posterior is computable, so neither
maximum likelihood nor exact EM applies. The variational autoencoder
responds with the Lesson 31 bound and an explicit choice of
approximating family: a Gaussian $q$ whose own parameters are produced by
a network from the observation. Encoding and decoding meet in the middle
through the ELBO.

<Widget type="math" id="com.github.richbai90.stats.33-continuous-latents.vae_elbo" />

The first term rewards reconstructions that explain the data; the second pins the
encoder's output near the prior. One gradient recipe trains both networks,
and the sampling inside ($\mathbf{z} = \boldsymbol\mu +
\boldsymbol\sigma \odot \boldsymbol\epsilon$) is the reparameterization
trick that made the whole thing differentiable.

<Widget type="stepper" id="com.github.richbai90.stats.33-continuous-latents.stepper_reparam" />

## Amortization and its failure mode

A single encoder network amortizes inference across the whole dataset:
each new point gets its posterior parameters in one forward pass. The
price is a biased approximation the EM loop of Lesson 31 never paid, and
the familiar failure is posterior collapse: the decoder grows powerful
enough to explain data without latents, the KL term wins, and the code
goes silent. The diagnostics are probabilistic, not folklore: watch the
KL term per dimension, exactly as
[Lesson 25](/course/stats/numerics) watched gradient norms.

<Widget type="quiz" id="com.github.richbai90.stats.33-continuous-latents.quiz_vae" />

<Widget type="flashcard" id="com.github.richbai90.stats.33-continuous-latents.card_reparam" />

<Widget type="flashcard" id="com.github.richbai90.stats.33-continuous-latents.card_collapse" />

## Teach it back

The ELBO and the reparameterization trick are the two pieces that make
the VAE trainable. Teach the nonlinear wall and the fix before the
unification lesson.

<Widget type="teach" id="com.github.richbai90.stats.33-continuous-latents.teach" />
