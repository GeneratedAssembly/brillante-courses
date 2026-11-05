---
title: Designing the Pipeline
description: The method-selection decision tree from MLE through MAP, VI, MCMC, and SMC, and the bounds that tell you which rung the problem is on. After MacKay, chapter 28, Kay, Vol. III, and the whole course applied to itself.
order: 43
section: module-5
---

# Designing the Pipeline

Forty-three lessons built an arsenal: sufficiency and bounds, Wiener
and Kalman, penalties and dictionaries, EM and the ELBO, chains and
clouds. This lesson is the dispatch table: which tool for which
problem, decided by properties you can check before writing a line of
algorithm code, and guarded by the bounds of [Module
1](/course/stats/crlb) throughout. After MacKay, chapter 28, and Kay,
Vol. III, applied to everything this course has covered.

## The triage

<Widget type="math" id="com.github.richbai90.stats.43-pipeline-design.master" />

Check identifiability first, the identifiability-first discipline of
[Lesson 1](/course/stats/observation-model). Then check the noise law,
the constraint geometry of [Lesson 20](/course/stats/convex-geometry),
and the posterior's shape. Each answer knocks out whole families of
methods, and what survives is the pipeline.

<Widget type="stepper" id="com.github.richbai90.stats.43-pipeline-design.stepper_triage" />

<Widget type="quiz" id="com.github.richbai90.stats.43-pipeline-design.quiz_rungs" />

## Bounds as rung detectors

<Widget type="math" id="com.github.richbai90.stats.43-pipeline-design.bounds" />

The bounds are not decoration; they are the diagnostics that place the
problem. A tight CRLB with a linear model says closed form: stop at
[Lesson 6](/course/stats/bayes-mmse). A CRLB the solver cannot reach,
with residuals that fail Gaussianity, says the likelihood geometry is
wrong and points down the Bayesian rungs. The ELBO gap of [Lesson
31](/course/stats/em-elbo) and the ESS of [Lesson
39](/course/stats/mcmc) are the same instrument at the variational and
sampling rungs: each bound prices the shortcut its rung takes.

<Widget type="quiz" id="com.github.richbai90.stats.43-pipeline-design.quiz_bounds" />

## Exactness when closed forms fail

When no rung is conjugate and the posterior is nasty, the exact
pipelines still exist: MCMC integrates anything smooth, SMC handles the
sequential and the multimodal, and the bridge between them is the
temperature ladder that anneals a tractable prior into the posterior.
The price is compute, and the price of *not* paying it is a point
estimate with no honest uncertainty, the failure mode this course
began by outlawing.

<Widget type="quiz" id="com.github.richbai90.stats.43-pipeline-design.quiz_smc_vs_mcmc" />

<Widget type="flashcard" id="com.github.richbai90.stats.43-pipeline-design.card_triage" />

<Widget type="flashcard" id="com.github.richbai90.stats.43-pipeline-design.card_price" />

## Teach it back

This is the course's final synthesis: the decision tree that chooses
the method. Teach it as the exam it is — triage, bounds as rung
detectors, and the exact pipelines that remain when closed forms fail.

<Widget type="teach" id="com.github.richbai90.stats.43-pipeline-design.teach" />
