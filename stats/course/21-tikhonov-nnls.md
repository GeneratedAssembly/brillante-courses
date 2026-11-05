---
title: Penalties and Constraints
description: Tikhonov regularization, weighted least squares, constrained least squares with KKT conditions, and projected-gradient NNLS. After Boyd and Vandenberghe, chapter 6 and chapter 5.
order: 21
section: module-3
---

# Penalties and Constraints

[Lesson 7](/course/stats/bayes-map#the-coincidence-that-opens-module-3) left
a formula on the table: the MAP estimator with a Gaussian prior is least
squares plus a quadratic penalty. This lesson takes that penalty seriously as
an engineering tool (after Boyd and Vandenberghe, chapter 6), and pairs it
with the other way of injecting knowledge, hard constraints, governed by the
KKT conditions of chapter 5. The two are the same act performed with
different severity: a prior that may be argued with (a penalty) and a prior
that may not (a constraint).

## Tikhonov regularization

<Widget type="math" id="com.github.richbai90.stats.21-tikhonov-nnls.tikhonov" />

Read the solution through the SVD of Lesson 19: every singular component is
multiplied by a filter factor $\sigma_i^{2}/(\sigma_i^{2} + \lambda)$, which
is nearly $1$ for strong directions and nearly $0$ for weak ones. The ridge
does not try to invert what the data barely observed: it declines, smoothly
and reversibly. The price is bias on every direction; the profit is that the
variance explosion of the condition number is gone. When the noise is white
and Gaussian, this estimator is exactly the Gaussian-prior MAP of
[Lesson 7](/course/stats/bayes-map#lmmse-the-best-linear-rule), with
$\lambda$ playing the role of the noise-to-prior variance ratio.

<Widget type="quiz" id="com.github.richbai90.stats.21-tikhonov-nnls.quiz_tikhonov" />

## Weighted least squares

Real noise is rarely white. If the covariance of $\mathbf{n}$ is
$\mathbf{C}$, the likelihood of Lesson 4 weights the residuals by the
precision $\mathbf{C}^{-1}$:

<Widget type="math" id="com.github.richbai90.stats.21-tikhonov-nnls.weighted" />

This is the Wiener filter of [Lesson 13](/course/stats/wiener) with the
Toeplitz structure removed: same whitening logic, same optimality claim,
now on generic $\mathbf{H}$. Weighting by precision is also the honest way
to combine sensors of unequal quality: the shot-noise-limited band gets
more say than the read-noise-limited one.

## Constrained least squares and the KKT system

When a constraint must hold exactly (nonnegative intensities, weights that
sum to one), the optimum is found at the boundary, and the gradient there
does not vanish; it is balanced by the constraint forces:

<Widget type="math" id="com.github.richbai90.stats.21-tikhonov-nnls.kkt" />

The multipliers are not bookkeeping; they are prices. The multiplier of the
sum-to-one constraint answers: how much would the objective improve if the
budget relaxed by one unit? A zero multiplier means the constraint was not
binding at all.

## Nonnegative least squares by projection

The workhorse solver for constrained problems is projected gradient: descend
freely, then project back onto the feasible set
([Lesson 20](/course/stats/convex-geometry)). On the orthant the projection
is a clip, so each iteration is one matrix-vector product plus one elementwise
maximum:

<Widget type="stepper" id="com.github.richbai90.stats.21-tikhonov-nnls.stepper_pg" />

<Widget type="quiz" id="com.github.richbai90.stats.21-tikhonov-nnls.quiz_nnls" />

## What carries forward

Penalties and constraints are now a pair of interchangeable priors, and the
quadratic penalty has a non-quadratic sibling waiting: replace the squared
norm with the $\ell_1$ norm and the estimate becomes sparse.
[Lesson 22](/course/stats/l1-sparsity) makes that trade, and the simplex
returns in [Lesson 24](/course/stats/unmixing) as the natural home of mixing
weights.

<Widget type="flashcard" id="com.github.richbai90.stats.21-tikhonov-nnls.card_filter" />

<Widget type="flashcard" id="com.github.richbai90.stats.21-tikhonov-nnls.card_kkt" />

## Teach it back

SVD filter factors and KKT prices are this module's working machinery —
Lesson 24 reuses both on the simplex. Teach the penalty–constraint pair
before moving on.

<Widget type="teach" id="com.github.richbai90.stats.21-tikhonov-nnls.teach" />
