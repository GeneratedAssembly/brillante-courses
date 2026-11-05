---
title: Maximum Likelihood
description: The likelihood geometry, the invariance property, asymptotics, and the MLE for the Gaussian linear model, plus how to get it numerically when algebra fails.
order: 4
section: module-1
---

# Maximum Likelihood

The CRLB says how well anyone could do. Maximum likelihood is the recipe
that usually gets there. Pick the parameter value that makes the observed
data most probable:

<Widget type="math" id="com.github.richbai90.stats.04-mle.definition" />

Working with the log-likelihood $\ell(\theta)$ instead of $p(x;\theta)$
turns products into sums, and the maximizer is unchanged because $\ln$ is
monotone. Geometrically: $\ell(\theta)$ is a curve (a surface for vector
parameters), and the MLE is its peak. When the peak is at a smooth
interior point, it is where the score vanishes, the likelihood equation
$V(\theta) = 0$.

<Widget type="interactive" id="com.github.richbai90.stats.04-mle.inter_score" />

Sweep the probe $\theta$ and watch the score. For the five-sample Gaussian
data embedded in the plot ($n = 5$, $\sum x_i = 20$, $\sigma^2 = 4$), the
score $V(\theta) = (\sum_i x_i - n\theta)/\sigma^2$ is a straight line
crossing zero exactly at $\bar{x} = 4$: the peak of the log-likelihood
*is* the zero of the score. Non-Gaussian likelihoods keep the geometry and
lose the straightness.

## Invariance: the free lunch

The MLE of any function of the parameter is the function of the MLE:

<Widget type="math" id="com.github.richbai90.stats.04-mle.invariance" />

This is a property of maximization, not of a clever proof: reparametrizing
the likelihood cannot move its peak. Estimate the Poisson rate $\lambda$
and you get the MLE of the mean inter-arrival time $1/\lambda$ free of
charge. One caution from Lesson 3's transformation rule still applies:
precision statements must be transported with the Jacobian; invariance
only moves the point estimate.

## Asymptotics: why MLE is the default

Three large-sample facts make MLE the workhorse:

- **Consistency.** $\hat\theta \to \theta$ as $n \to \infty$ (under
  regularity).
- **Asymptotic efficiency.** The variance of $\hat\theta$ approaches the
  CRLB; the bound is *achievable* in the limit even when no finite-$n$
  efficient estimator exists.
- **Asymptotic normality.**

<Widget type="math" id="com.github.richbai90.stats.04-mle.asymptotic" />

The last line is the practical one: for large $n$, the MLE behaves like
the truth plus Gaussian noise of variance $I^{-1}(\theta)$. That is the
Lesson 3 bound, attained. This is why engineering practice reports
$\hat\theta \pm \sqrt{I^{-1}}$ as error bars without further ceremony.

## The Gaussian linear model

The single most reused MLE in signal processing: a linear forward model
with Gaussian noise of known variance.

<Widget type="stepper" id="com.github.richbai90.stats.04-mle.stepper_linear" />

The normal equations are the whole story: the least-squares solution *is*
the MLE for Gaussian noise. This equivalence carries through the course:
Wiener filtering (Module 2), Tikhonov regularization (Module 3), and the
Gaussian posterior mean (Lesson 6) are all the same normal equations in
different clothing.

<Widget type="quiz" id="com.github.richbai90.stats.04-mle.quiz_normal" />

## When algebra fails: numerical MLE

Real likelihoods (mixture models, event sensors, latent variables) do
not have closed-form peaks. The workhorse is **Newton–Raphson** (or its
statistical variant, **Fisher scoring**), which iterates

<Widget type="math" id="com.github.richbai90.stats.04-mle.newton" />

where $\mathbf{H}$ is the Hessian of $\ell$ (or its expected value,
$-\mathbf{I}(\theta)$, for scoring). Each step climbs the likelihood
surface quadratically fast near the peak. The failure modes matter:
multimodal likelihoods trap the iteration in a wrong peak, so always
start from several spread-out initializations and check the score is zero
and the Hessian negative-definite at the answer. Lesson 25 returns to
this geometry with the full convex-optimization toolkit.

<Widget type="quiz" id="com.github.richbai90.stats.04-mle.quiz_newton" />

## Check yourself

<Widget type="flashcard" id="com.github.richbai90.stats.04-mle.card_invariance" />

<Widget type="flashcard" id="com.github.richbai90.stats.04-mle.card_asymptotic" />

## Teach it back

The normal-equations equivalence carries through Wiener filtering,
Tikhonov regularization, and the Gaussian posterior mean. Make sure you
can teach it before the course leans on it.

<Widget type="teach" id="com.github.richbai90.stats.04-mle.teach" />
