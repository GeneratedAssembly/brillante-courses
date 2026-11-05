---
title: Poisson Counting and Exponential Families
description: The exponential family makes every lesson so far mechanical, and photon counting, the physical model behind Modules 3 and 5, is its cleanest case.
order: 5
section: module-1
---

# Poisson Counting and Exponential Families

A remarkable fraction of the models in this course (Gaussian, Poisson,
Bernoulli, exponential, multinomial) share one shape. Recognizing it
turns Lessons 2 through 4 from case-by-case derivations into one
mechanical recipe.

## The exponential family

A one-parameter distribution is in the **exponential family** when the
density or mass function can be written as

<Widget type="math" id="com.github.richbai90.stats.05-poisson.expfam" />

with **natural parameter** $\eta$, **natural statistic** $T(x)$, and a
normalizer $A(\eta)$ that does not involve the data. The factorization
theorem reads this at a glance: $T(X)$ is sufficient. The family is also
complete, so Lehmann–Scheffé applies: any unbiased function of $T$ is the
MVUE. And the Fisher information has the closed form

<Widget type="math" id="com.github.richbai90.stats.05-poisson.fim_expfam" />

One derivative of the normalizer replaces the whole score-variance
computation. For $n$ i.i.d. samples the information multiplies by $n$,
and the CRLB for any unbiased estimator of $g(\eta)$ is
$g'(\eta)^2/(n A''(\eta))$.

## Photon counting

The physical case study: a source emits photons at rate $\lambda$ (the
parameter); a detector integrates for exposure time $T$ and counts $N$
photo-events (the data). Shot noise makes $N$ Poisson:

<Widget type="math" id="com.github.richbai90.stats.05-poisson.model" />

This model is the ground truth for optical detection, and its
non-Gaussian character is not academic: at low flux the counts are small
integers, the Gaussian approximation collapses, and the full Poisson
likelihood is the only honest one. The CRLB for event-based
sensors course builds its entire spectral Fisher
machinery on exactly this likelihood.

<Widget type="interactive" id="com.github.richbai90.stats.05-poisson.inter_likelihood" />

The Poisson log-likelihood in $\lambda$ is concave with a single peak;
the interactive plots $\ell(\lambda) = N\ln(\lambda T) - \lambda T$ for a
fixed count $N = 37$ and lets you sweep the exposure time $T$. Longer
exposure moves the peak to smaller $\lambda$ (the same count spread over
more time means a dimmer source) and flattens it, because the
information per unit exposure grows with $T$.

## The Poisson MLE

<Widget type="stepper" id="com.github.richbai90.stats.05-poisson.stepper_mle" />

The MLE is the empirical rate $\hat\lambda = N/(nT)$: total counts
divided by total exposure. It is unbiased (the Poisson mean is linear in
$\lambda$), it is a function of the sufficient statistic $\sum_i N_i$,
and it is efficient: the Poisson family is exponential, the
log-likelihood is smooth, and the bound is met exactly.

## The Poisson CRLB

The Fisher information for one count is $T/\lambda$ (from
$A''(\eta)$ with $\eta = \ln\lambda$), so for $n$ exposures:

<Widget type="math" id="com.github.richbai90.stats.05-poisson.crlb" />

Read the physics: relative precision scales as $1/\sqrt{\text{total
counts}}$. Estimating a rate to 1% needs $10^4$ detected photons
regardless of how they are distributed across exposures; shot noise is a
budget, not a rate. The same square-root law governs spectroscopy,
imaging, and every shot-noise-limited measurement in Module 3, where
$\lambda$ becomes a whole non-negative spectrum and the CRLB becomes a
matrix over bins.

<Widget type="quiz" id="com.github.richbai90.stats.05-poisson.quiz_shot" />

## Exponential family = one derivation, many models

The moral of this lesson: for any exponential family, the
workflow of Lessons 2–4 collapses to three steps. Read $T(x)$ and
$A(\eta)$ off the density, apply $\hat\eta$ from $A'(\hat\eta) = T/n$,
transport back through $\eta(\theta)$. The [first problem
set](/course/stats/assign-1a) exercises this on the exponential
distribution, whose natural parameter is $-\lambda$, a small trap worth
hitting here rather than on an exam.

<Widget type="quiz" id="com.github.richbai90.stats.05-poisson.quiz_expfam" />

## Check yourself

<Widget type="flashcard" id="com.github.richbai90.stats.05-poisson.card_natural" />

<Widget type="flashcard" id="com.github.richbai90.stats.05-poisson.card_shot" />

## Teach it back

The exponential-family recipe and the shot-noise law are the mechanical
and physical backbone of Modules 3 and 5. Teach both back before moving
on.

<Widget type="teach" id="com.github.richbai90.stats.05-poisson.teach" />
