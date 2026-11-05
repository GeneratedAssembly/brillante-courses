---
title: Sequential Inference End to End
description: The full Bayesian pipeline for non-Gaussian inverse problems; the filtering recursion, a Poisson photon-counting update, and a particle-filter worked example from prior to credible interval. After MacKay, chapter 30, and Kay, Vol. III, chapter 11.
order: 42
section: module-5
---

# Sequential Inference End to End

Modules 1 through 4 built estimators; this lesson runs the complete
Bayesian pipeline on a problem none of them solves in closed form: a
photon counter whose intensity drifts, observed through Poisson noise,
tracked by particles, and reported as a credible interval. Every piece
exists from an earlier lesson; the assembly is the new part. After
MacKay, chapter 30, and Kay, Vol. III, chapter 11.

## The filtering recursion

<Widget type="math" id="com.github.richbai90.stats.42-sequential-inference.recursion" />

Predict through the dynamics, correct through the likelihood: the
two-line recursion that [Lesson 16](/course/stats/kalman) solved in
Gaussian arithmetic and [Lesson 41](/course/stats/particle-filtering)
solves in particle arithmetic. The prediction step integrates over the
old belief; the correction step reweights by the new evidence. When
neither step is conjugate, the particles carry the belief and the
algebra disappears.

<Widget type="quiz" id="com.github.richbai90.stats.42-sequential-inference.quiz_predict" />

## The conjugate waypoint

<Widget type="math" id="com.github.richbai90.stats.42-sequential-inference.poisson_gamma" />

Poisson counts with a Gamma prior stay conjugate: add the counts to the
shape, one to the rate. The intensity posterior after two exposures is
a Gamma whose credible interval is exact arithmetic, and it is the
benchmark the particle filter must match when the intensity stops
being constant. [Lesson 5](/course/stats/mle-poisson) derived the
likelihood; here the same Poisson law feeds a full posterior instead of
a point estimate.

<Widget type="stepper" id="com.github.richbai90.stats.42-sequential-inference.stepper_pipeline" />

## Why the particle cloud, not the Kalman update

Poisson noise is multiplicative in the intensity, the drift is
nonlinear, and the posterior after a few corrections is skewed with a
heavy right tail: the credible interval is not symmetric around the
mean, so every Gaussian summary lies by construction. The Kalman update
of [Lesson 16](/course/stats/kalman) would also have needed the
intensity linearized per step; the particle cloud tracks the skew for
free. Problem Set 5B, B4 prices the conjugate update against the
frequentist count, and B5 asks which pipeline the residuals deserve.

<Widget type="quiz" id="com.github.richbai90.stats.42-sequential-inference.quiz_why_particles" />

<Widget type="math" id="com.github.richbai90.stats.42-sequential-inference.credible" />

<Widget type="quiz" id="com.github.richbai90.stats.42-sequential-inference.quiz_prior" />

<Widget type="flashcard" id="com.github.richbai90.stats.42-sequential-inference.card_recursion" />

<Widget type="flashcard" id="com.github.richbai90.stats.42-sequential-inference.card_conjugate" />

## Teach it back

The assembly in this lesson is the course's full pipeline, run on a
problem no closed form solves. Teach the recursion, the conjugate
waypoint, and why particles before the dispatch table.

<Widget type="teach" id="com.github.richbai90.stats.42-sequential-inference.teach" />
