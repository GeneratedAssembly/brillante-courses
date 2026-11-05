---
title: Sparsity as a Prior
description: LASSO and basis pursuit, soft thresholding, ISTA and FISTA, and why the L1 ball is diamond-shaped. After Elad, chapters 1 and 6, with the geometry of Boyd and Vandenberghe chapter 3.
order: 22
section: module-3
---

# Sparsity as a Prior

The ridge penalty of Lesson 21 shrinks every coefficient a little. Many
physical signals ask for the opposite: most coefficients should be exactly
zero, a few should be estimated well. A spike train, a spectrum with a few
lines, an image of edges on flats: these are sparse, and the prior that
says so is the $\ell_1$ norm. After Elad, chapters 1 and 6, with the ball
geometry of [Lesson 20](/course/stats/convex-geometry). This is the
deterministic face of [Lesson 6](/course/stats/bayes-mmse): shrinkage, but
with a prior that has corners.

## The LASSO and basis pursuit

<Widget type="math" id="com.github.richbai90.stats.22-l1-sparsity.lasso" />

Basis pursuit is the same idea at the noiseless limit: minimize
$\|\mathbf{x}\|_1$ subject to $\mathbf{H}\mathbf{x} = \mathbf{y}$ exactly.
Both are convex (a norm ball plus a quadratic), so every local minimum is
global, and both prefer sparse solutions for a geometric reason the next
section makes visible.

## Why corners are sparse

<Widget type="math" id="com.github.richbai90.stats.22-l1-sparsity.geometry" />

The $\ell_2$ ball is round and touches a typical solution surface at a
generic point (all coordinates nonzero). The $\ell_1$ ball is a diamond, and
its boundary is covered by corners and edges that live on the axes and
coordinate planes. First contact between the expanding penalty surface and
the data-fit surface therefore happens, with high probability, at a point
with several coordinates exactly zero. Sparsity is not a hope appended to
the optimization; it is the shape of the penalty.

<Widget type="quiz" id="com.github.richbai90.stats.22-l1-sparsity.quiz_lasso" />

## Soft thresholding and ISTA

The ridge had a closed form; the LASSO has a closed form one step at a time.
Proximal gradient splits the objective into the smooth quadratic (gradient
step) and the nonsmooth norm (exact minimization). The exact minimization
half has a name and a closed form of its own:

<Widget type="math" id="com.github.richbai90.stats.22-l1-sparsity.prox" />

The proximal step pulls every entry toward zero by the threshold, and
entries that cross it die on the axis. One gradient step plus one prox is
one ISTA iteration:

<Widget type="stepper" id="com.github.richbai90.stats.22-l1-sparsity.stepper_ista" />

The resulting algorithm (ISTA, iterative shrinkage-thresholding) is the
ridge iteration of Lesson 21 with the shrinkage replaced by killing. It
inherits the convergence rate of gradient descent, and acceleration tricks
(FISTA momentum) restore a nearly second-order rate at first-order cost,
after Elad chapter 6.

<Widget type="quiz" id="com.github.richbai90.stats.22-l1-sparsity.quiz_ista" />

## The bias-sparsity bargain

Soft thresholding biases every surviving coefficient by $-\lambda\,\mathrm{sign}$: sparsity is bought with shrinkage. Variants tune the bargain:
the unbiased LASSO refinement debiases after support recovery, and
nonconvex penalties sharpen corners further at the cost of global guarantees.
The course stays convex: the guarantees are worth more than the last percent
of bias.

## What carries forward

A prior with corners turned estimation into model selection: the support
(set of nonzero coefficients) is now an object the algorithm outputs. Module
4 will meet the same object from the probabilistic side (latent structure,
mixture weights, the Dirichlet), where sparsity reappears as concentration.
Before that, [Lesson 23](/course/stats/dictionaries) asks the question the
fixed basis $\mathbf{H}$ avoided: where did the columns come from, and can
they be learned?

<Widget type="flashcard" id="com.github.richbai90.stats.22-l1-sparsity.card_soft" />

<Widget type="flashcard" id="com.github.richbai90.stats.22-l1-sparsity.card_geometry" />

## Teach it back

Soft thresholding is the operator the sparsity half of this course runs
on, and the corner geometry is the reason it works. Teach both before
the dictionaries lesson.

<Widget type="teach" id="com.github.richbai90.stats.22-l1-sparsity.teach" />
