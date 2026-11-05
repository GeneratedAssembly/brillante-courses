---
title: Monte Carlo
description: Estimating expectations by sampling, the root-N error bar, importance sampling and its ESS, and Monte Carlo evaluation of estimators against theoretical bounds. After MacKay, chapter 29, and Kay, Vol. III, chapter 11.
order: 38
section: module-5
---

# Monte Carlo

An expectation you cannot integrate, you can sample. Monte Carlo
replaces the intractable sums of Module 4 with random numbers whose
average converges to the answer at the universal rate $1/\sqrt{N}$:
dimension-free, derivative-free, and honest about its own error. After
MacKay, chapter 29, with Kay, Vol. III, chapter 11, where simulation
becomes the referee for the bounds of [Module 1](/course/stats/crlb).

## The sample average

<Widget type="math" id="com.github.richbai90.stats.38-monte-carlo.mc_estimate" />

Draw $\mathbf{z}^{(i)}$ from $p$ and average the function: the estimate
is unbiased and its standard error is $\sigma/\sqrt{N}$, where
$\sigma$ is the standard deviation of the summand, not of the
distribution sampled. Four times the samples buy one extra digit. The
rate is dimension-free: a thousand-dimensional integral costs the same
per digit as a one-dimensional one, which is the entire case for
sampling over grids. [Lesson 25](/course/stats/numerics) watched
deterministic iterations converge; this is the stochastic sibling.

<Widget type="interactive" id="com.github.richbai90.stats.38-monte-carlo.inter_error" />

<Widget type="quiz" id="com.github.richbai90.stats.38-monte-carlo.quiz_rate" />

## Importance sampling

<Widget type="math" id="com.github.richbai90.stats.38-monte-carlo.importance" />

Sampling from $p$ directly is often the impossible part. Importance
sampling samples a proposal $q$ and reweights by $p/q$: exact in
expectation, but the weights carry the mismatch, and the effective
sample size, not the nominal one, says what the estimate is worth.

$$\mathrm{ESS} = \frac{\left(\sum_i w_i\right)^2}{\sum_i w_i^2}$$

A proposal with thin tails where $p$ is heavy produces a few huge
weights, an ESS of three, and an error bar that lies. Problem Set 5A,
A3 works a five-point case where the ESS is barely two.

<Widget type="quiz" id="com.github.richbai90.stats.38-monte-carlo.quiz_is" />

## Error bars you can defend

<Widget type="math" id="com.github.richbai90.stats.38-monte-carlo.error_bars" />

The central limit theorem turns the $1/\sqrt{N}$ rate into a
reportable interval: $\hat\mu \pm 1.96\,\hat\sigma/\sqrt{N}$ covers the
truth about ninety-five percent of the time, and the batch-means trick
estimates $\hat\sigma$ even under dependence. A Monte Carlo result
without an error bar is a rumor.

<Widget type="stepper" id="com.github.richbai90.stats.38-monte-carlo.stepper_referee" />

Kay III's discipline closes the module's first half: simulate the
estimator you designed in Module 1, count its mean-squared error over
thousands of synthetic datasets, and lay the empirical cloud against
the Cramér–Rao bound. A bound the estimator never touches in
simulation is either loose or a bug; the simulation tells you which.
Problem Set 5B, B1 runs the comparison on a fixed replicate set.

<Widget type="quiz" id="com.github.richbai90.stats.38-monte-carlo.quiz_referee" />

<Widget type="flashcard" id="com.github.richbai90.stats.38-monte-carlo.card_rate" />

<Widget type="flashcard" id="com.github.richbai90.stats.38-monte-carlo.card_ess" />

## Teach it back

The effective-sample-size discipline below decides whether every
sampler after this lesson can be trusted. Teach the root-N rate and the
weight-collapse failure before moving on.

<Widget type="teach" id="com.github.richbai90.stats.38-monte-carlo.teach" />
