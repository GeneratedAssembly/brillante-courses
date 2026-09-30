---
title: The Poisson Count Model
description: The simplest informative likelihood for sparse asynchronous events — PMF, score, and the Δt/Λ information law, derived line by line.
order: 4
---

Event sensors emit sparse, asynchronous counts. The simplest model for a
count — and the foundation the sensor lessons extend — is the **Poisson
distribution**: the probability of observing $k$ events in an interval of
length $\Delta t$ when events arrive at mean rate $\Lambda$.

## The PMF and its log-likelihood

<Widget type="math" id="com.github.richbai90.crlb2.math_poisson_pmf" />

<Widget type="math" id="com.github.richbai90.crlb2.math_poisson_ll" />

Two terms die when we differentiate: $k \ln \Delta t$ and $\ln k!$ do not
depend on $\Lambda$. Only $k \ln \Lambda$ and $-\Lambda \Delta t$ carry
information about the rate.

## The score and the count Fisher information

<Widget type="math" id="com.github.richbai90.crlb2.math_poisson_score" />

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_poisson_score" />

<Widget type="math" id="com.github.richbai90.crlb2.math_poisson_fim" />

The same result via the covariance form:
$\operatorname{Var}(K) = \Lambda \Delta t$ for Poisson counts, so

$$I(\Lambda) = \frac{\operatorname{Var}(K)}{\Lambda^2} = \frac{\Lambda\,\Delta t}{\Lambda^2} = \frac{\Delta t}{\Lambda}.$$

Two forms, one answer — the equivalence of the
[Fisher lesson](/course/crlb/fisher) doing real work.

If instead we parametrize by the bin mean $\mu = \Lambda\,\Delta t$ (the
expected count per bin), the information is $I(\mu) = 1/\mu$: each extra
expected event buys *less* than the last, proportionally. These two facts —
$I(\mu) = 1/\mu$ and $I(\Lambda) = \Delta t/\Lambda$ — are among the
[Lean-verified](/course/crlb/lean) identities of the course.

## Explore the trade-off

Information about the rate *falls* as the rate grows: the Poisson variance
$\operatorname{Var}(K) = \Lambda \Delta t$ grows as fast as the mean, and
the relative precision $\operatorname{Var}(K)/\Lambda^2$ degrades. Quiet
regimes are informative regimes.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_poisson_information" />

## Independence is a luxury, means are a necessity

One subtlety that later lessons inherit verbatim: computing the *zero-mean
score* over many Poisson counts requires only each count's mean —
$\mathbb{E}[K] = \Lambda\,\Delta t$ — and linearity of expectation. The
counts do **not** have to be independent for the score to vanish. Full
independence is needed only to write the joint PMF as a product of
per-bin PMFs. When the [point-process lesson](/course/crlb/point-process)
bins event streams, this distinction survives: the Fisher identity uses
first moments, while independence constructs the likelihood.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_poisson_information" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_means_vs_independence" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_poisson_information" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_bin_mean" />