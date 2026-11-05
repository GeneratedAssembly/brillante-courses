---
title: MAP, LMMSE, and the Road to Regularization
description: Two more estimators from the same posterior (the mode and the best linear rule), and the algebraic coincidence that opens Module 3.
order: 7
section: module-1
---

# MAP, LMMSE, and the Road to Regularization

The posterior is the complete inference; an estimator is one question
addressed to it. Lesson 6 asked for the mean. This lesson asks for the
**mode** and then for the best answer from a deliberately smaller class,
and ends at a formula that Module 3 will turn into a full theory of
regularization.

## MAP: the posterior mode

The **maximum a posteriori** estimator picks the highest point of the
posterior:

<Widget type="math" id="com.github.richbai90.stats.07-map.definition" />

Dropping the $p(x)$ (it does not involve $\theta$) leaves "likelihood
times prior", or in logs "log-likelihood minus prior penalty". MAP is
the likelihood of Lesson 4 with a prior term attached; MLE is exactly
the flat-prior case.

For a Gaussian likelihood and a Gaussian prior, MAP is the same weighted
average as the MMSE; the Gaussian posterior is symmetric, so its mean
and mode agree:

<Widget type="stepper" id="com.github.richbai90.stats.07-map.stepper_map" />

The Gaussian MAP lands on the same $\hat\theta$ as Lesson 6's MMSE. The
two estimators part company for skewed posteriors (Poisson, exponential,
bounded parameters), where the mode slides into the boundary while the
mean stays interior. Which to use is a decision about the loss you will
actually pay for: mode for "one true value" narratives, mean for squared
error.

<Widget type="quiz" id="com.github.richbai90.stats.07-map.quiz_mode" />

## LMMSE: the best linear rule

Sometimes you do not want to model the prior at all; you have moments
and nothing more. The **linear minimum mean-squared error** estimator
restricts the search to affine rules $\hat\theta = \mathbf{a}^{\mathsf T}\mathbf{x} + b$
and finds the best in that class from second moments alone:

<Widget type="math" id="com.github.richbai90.stats.07-map.lmmse" />

No distributional assumption beyond covariances; Gaussian or not, this is
the best linear estimator, and for jointly Gaussian data it is the best
estimator, period (the Gaussian posterior mean is linear). The
$\mathbf{C}_{x\theta}$ term is the cross-covariance between data and
parameter, the statistical echo of the forward operator $\mathbf{h}$.
Module 2's Wiener filter is LMMSE with past signal samples as the data;
Module 2's normal equations and this formula are the same object.

<Widget type="quiz" id="com.github.richbai90.stats.07-map.quiz_lmmse" />

## The coincidence that opens Module 3

Rewrite the Gaussian MAP objective once more:

<Widget type="math" id="com.github.richbai90.stats.07-map.ridge" />

Three equivalent readings of one line:

- **Bayesian**: the posterior mode under a Gaussian prior.
- **Deterministic**: least squares with a quadratic penalty on the
  distance of $\theta$ from a preferred value, **Tikhonov
  regularization**.
- **Geometric**: the point balancing data fit against prior plausibility,
  with $\sigma^2/\sigma_0^2$ as the exchange rate.

The Bayesian and deterministic schools arrive at the same estimator by
different doors. Module 3 takes the deterministic door and pushes much
harder: physical constraints (non-negativity, energy), sparsity penalties
in place of the quadratic, and the ill-posedness that makes the penalty
load-bearing rather than decorative. The formula above is the
$\lambda \mathbf{I}$ you will meet again as the ridge term.

<Widget type="quiz" id="com.github.richbai90.stats.07-map.quiz_bridge" />

## Module 1 in one sentence

Write the generative model; find what the data suffices to know; bound
the achievable precision; maximize the likelihood or average the
posterior; and when the model is Gaussian and linear, everything
collapses to normal equations. The problem sets that follow run this
chain on ten problems.

<Widget type="flashcard" id="com.github.richbai90.stats.07-map.card_map" />

<Widget type="flashcard" id="com.github.richbai90.stats.07-map.card_lmmse" />

## Teach it back

Module 1 ends here, and Module 3 opens with this lesson's final formula.
Teach the whole chain — model, sufficiency, bound, likelihood, posterior
— before you walk through the deterministic door.

<Widget type="teach" id="com.github.richbai90.stats.07-map.teach" />
