---
title: The Cramér–Rao Bound
description: The Fisher information converts noise level into a hard floor on estimator variance; scalar and vector forms, efficiency, BLUE, and transformations.
order: 3
section: module-1
---

# The Cramér–Rao Bound

Lesson 1's second identifiability check needs a number: how well can the
data possibly constrain $\theta$? The Cramér–Rao lower bound (CRLB) is
that number. No unbiased estimator can beat it, and estimators that touch
it (**efficient** estimators) are as good as unbiased estimation can
get.

## The scalar bound

For a single unknown with a twice-differentiable likelihood:

<Widget type="math" id="com.github.richbai90.stats.03-crlb.crlb_scalar" />

The denominator is the **Fisher information** $I(\theta)$, the variance
of the score, derived from first principles in the companion
Cramér–Rao course. The
reading is physical. A steep log-likelihood around the truth means the
data distinguishes $\theta$ from $\theta + \mathrm{d}\theta$ strongly,
$I$ is large, and the variance floor is low. Flat likelihoods leave room
for noise to mimic parameter changes, and the floor rises. Information
has units of inverse variance; the bound is its reciprocal.

<Widget type="stepper" id="com.github.richbai90.stats.03-crlb.stepper_crlb" />

The engine of the proof is Cauchy–Schwarz on two zero-mean random
variables: the score $V$ and the estimation error $\hat\theta - \theta$.
Their covariance is exactly $1$ for unbiased $\hat\theta$ (a small
algebraic miracle), so the product of their variances is at least $1$.

## Efficiency and the Gaussian case

An unbiased estimator that attains the bound is **efficient**. Efficiency
is special, not generic: it happens when the estimation error and the
score are proportional random variables, which for i.i.d. models means
the log-likelihood must be quadratic in $\theta$. Gaussian families are
exactly the case where this holds, which is why Gaussian examples always
come out clean:

- $\bar{X}$ for a Gaussian mean of known variance: $\operatorname{Var} =
  \sigma^2/n = I^{-1}$. Efficient.
- $\tilde{X}$ for a Gaussian variance with known mean: the bound is
  $2\sigma^4/n$, and the unbiased sample variance misses it by a factor
  that only vanishes slowly. It is not efficient: the MVUE is
  asymptotically good but never touches the bound for finite $n$.

When no efficient estimator exists, the MVUE of Lesson 2 is the honest
target; the CRLB remains the scorecard.

## The vector bound

With $p$ unknowns, the scalar variance floor becomes a matrix
inequality, and the Fisher information becomes a matrix too:

<Widget type="math" id="com.github.richbai90.stats.03-crlb.fim" />

<Widget type="math" id="com.github.richbai90.stats.03-crlb.crlb_vector" />

The matrix $\mathbf{I}(\theta) - \mathbf{J}(\theta)$ on the right is
positive semidefinite for every unbiased $\hat{\boldsymbol\theta}$, where
$\mathbf{J}$ is the covariance matrix of the estimate. Diagonal entries
bound each parameter separately; off-diagonal structure is the coupling
story. **Large off-diagonal entries in $\mathbf{I}^{-1}$ mean the data
cannot separate those parameters**: trying to estimate two overlapping
frequencies from one short record gives a nearly singular information
matrix; the parameters blur into each other, and no algorithm fixes that.
The fix is more data (longer record, more sensors), exactly as in Lesson
1's identifiability check.

This course keeps the vector machinery to a minimum, but the companion
course (The Cramér–Rao Bound for Event-Based
Sensors) derives the spectral Fisher matrix from
first principles for Poisson event data, the deep version of everything
this lesson states abstractly.

<Widget type="quiz" id="com.github.richbai90.stats.03-crlb.quiz_fim" />

## Transformations and BLUE

Two standard extensions cover most coursework:

**Transformed parameters.** The CRLB is not invariant under
reparametrization, but it transports: for $\alpha = g(\theta)$ with
differentiable $g$,

<Widget type="math" id="com.github.richbai90.stats.03-crlb.transform" />

Estimating $1/\lambda$ instead of $\lambda$ changes the bound by
$g'(\lambda)^2 = 1/\lambda^4$; precision statements always name the
parametrization.

**BLUE.** If the estimator is restricted to be **linear in the data** and
unbiased (the *Best Linear Unbiased Estimator*), the Gaussian assumption
drops out. For a Gaussian mean with known variance, $\bar{X}$ is BLUE
(and efficient); for non-Gaussian noise with known covariance
$\mathbf{C}$, the weighted least-squares form
$\hat\theta = (\mathbf{1}^{\mathsf T}\mathbf{C}^{-1}\mathbf{1})^{-1}\mathbf{1}^{\mathsf T}\mathbf{C}^{-1}\mathbf{y}$
is BLUE. Module 2's Wiener filter is this idea running across time.

<Widget type="quiz" id="com.github.richbai90.stats.03-crlb.quiz_blue" />

## Check yourself

<Widget type="flashcard" id="com.github.richbai90.stats.03-crlb.card_fisher" />

<Widget type="flashcard" id="com.github.richbai90.stats.03-crlb.card_efficient" />

## Teach it back

Fisher information is the scorecard every later estimator is measured
against, from photon counting to the Kalman gain. Explain the floor in
your own words before moving on.

<Widget type="teach" id="com.github.richbai90.stats.03-crlb.teach" />
