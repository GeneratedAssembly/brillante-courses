---
title: Particle Filtering
description: Sequential Monte Carlo for state tracking, SIS weight collapse, effective sample size, systematic resampling, and the bootstrap proposal. After Kay, Vol. III, chapter 11, and Doucet and Johansen, 2011.
order: 41
section: module-5
---

# Particle Filtering

The Kalman filter of [Lesson 16](/course/stats/kalman) is exact and
linear-Gaussian, and nothing else. Particle filtering keeps the
recursive structure (predict, weight, resample) but represents the
belief with a cloud of samples, so the dynamics may be nonlinear and
the noise may be anything you can evaluate. After Kay, Vol. III,
chapter 11, and Doucet and Johansen, 2011.

## The recursion, carried by particles

<Widget type="math" id="com.github.richbai90.stats.41-particle-filtering.sis" />

Sequential importance sampling propagates each particle through the
transition law and multiplies its weight by the likelihood of the new
observation. The weighted cloud *is* the posterior: its mean is the
[Lesson 38](/course/stats/monte-carlo) estimator, its spread the
credible band, and no Gaussianity is claimed anywhere.

<Widget type="quiz" id="com.github.richbai90.stats.41-particle-filtering.quiz_collapse" />

## Degeneracy and the ESS

<Widget type="math" id="com.github.richbai90.stats.41-particle-filtering.ess" />

Weight collapse is the sequential form of the importance-sampling
failure: after enough steps, one particle owns the posterior and the
rest are dead weight. The effective sample size counts the living;
when it drops below a fraction of the cloud, resample: draw the next
generation from the weighted empirical distribution, reset the weights,
and accept the variance cost as the price of staying alive.

<Widget type="interactive" id="com.github.richbai90.stats.41-particle-filtering.inter_ess" />

<Widget type="stepper" id="com.github.richbai90.stats.41-particle-filtering.stepper_bootstrap" />

<Widget type="quiz" id="com.github.richbai90.stats.41-particle-filtering.quiz_resample" />

## The bootstrap filter and its choices

Resampling from the prior-derived cloud is the *bootstrap* filter:
proposal = transition, weights = likelihood only, and every choice
(when to resample, how many particles, how to jitter degenerate copies)
becomes a tuning knob with an ESS readout. The optimal proposal would
condition on the observation before propagating, exactly the
lookahead that [Lesson 14](/course/stats/spectrum-estimation)'s
model-based estimators applied off-line; it costs a per-particle
inference, and the ESS gain decides whether the inference is worth it.
Problem Set 5B, B2 and B3 walk both steps with hand-checkable numbers.

<Widget type="flashcard" id="com.github.richbai90.stats.41-particle-filtering.card_bootstrap" />

<Widget type="flashcard" id="com.github.richbai90.stats.41-particle-filtering.card_degeneracy" />

## Teach it back

Weight collapse is the failure mode the final pipeline must manage.
Teach the SIS recursion, the ESS readout, and what resampling buys
before the worked example.

<Widget type="teach" id="com.github.richbai90.stats.41-particle-filtering.teach" />
