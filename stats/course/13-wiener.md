---
title: The Wiener Filter
description: Optimum linear filtering through the Wiener–Hopf equations, the orthogonality principle, and the causal solution via spectral factorization. After Hayes, chapter 7.
order: 13
section: module-2
---

# The Wiener Filter

[Lesson 7](/course/stats/bayes-map#lmmse-the-best-linear-rule) priced the
best *linear* rule for static data: the LMMSE estimator is a covariance
solve, and with jointly Gaussian data it is also the full MMSE. Wiener's
question is the same one with time in it: estimate a signal $x(n)$ from
observations $y(n)$ corrupted by noise $v(n)$, using a linear filter, and
make the mean-squared error as small as algebra allows. The answer is one
normal equation, one orthogonality principle, and, when real-time
operation is required, one spectral factorization. This is the master
model again, $\mathbf{y} = \mathbf{h}(\boldsymbol\theta) + \mathbf{n}$,
with the estimation target promoted from a constant to a process.

## The normal equations

Take an $M$-tap FIR estimate $\hat{x}(n) = \sum_{i=0}^{M-1} c(i)\,
y(n-i)$ and minimize the mean-squared error over the taps:

<Widget type="math" id="com.github.richbai90.stats.13-wiener.normal" />

Setting the gradient to zero leaves the **orthogonality principle**: at the
optimum, the error is uncorrelated with every observation the filter uses.
Geometrically, $\hat{x}$ is the projection of $x$ onto the span of the
data; no linear filter can squeeze out anything more, because whatever
correlation remained would define a better one. The matrix $\mathbf{R}_y$
is Toeplitz ([Lesson 10](/course/stats/random-processes)), so
Levinson-class solvers from
[Lesson 12](/course/stats/levinson-lattice) apply unchanged: structure
discounts the solve here exactly as it did there.

## The price

<Widget type="math" id="com.github.richbai90.stats.13-wiener.mmse" />

The error formula is the Gram–Schmidt ledger of
[Lesson 6](/course/stats/bayes-mmse) in filter form: total power minus the
power the projection removed.

## Filtering, smoothing, prediction

One normal equation, three regimes; they differ only in which lags the
filter may touch:

- **Filtering**: estimate $x(n)$ from present and past observations only.
  Real time; the causal design below.
- **Smoothing**: estimate $x(n)$ from observations centered on $n$,
  future included. Offline; strictly more accurate.
- **Prediction**: estimate a future value of $x(n)$ itself. The one-step
  predictor is exactly the AR recursion of
  [Lesson 11](/course/stats/signal-modeling).

## The noncausal solution

Drop causality first: the estimator may be any $H(f)$ applied to the
whole record. Then the error spectrum splits cleanly and the problem
decomposes frequency by frequency:

<Widget type="stepper" id="com.github.richbai90.stats.13-wiener.stepper_noncausal" />

The result is a soft SNR weighting: pass what the signal dominates, reject
what the noise dominates. Nothing sharp happens at any frequency. Wiener
filtering is Bayesian shrinkage spread across a band.

## Going causal

Real-time operation forbids the future, and the price is exact:

<Widget type="math" id="com.github.richbai90.stats.13-wiener.causal" />

Whiten the observations with the minimum-phase factor $Q$ of the *total*
spectrum $S_y = S_x + S_v$; the innovations that survive are uncorrelated
across time, so the optimal post-filter can only use their *positive-time*
part; that is the projection $[\cdot]_{+}$, the same projection
principle in the time domain. Dropping the negative-time half of the
whitened cross-spectrum is the entire cost of causality: the causal filter
is never better than the noncausal one, and it is worse exactly by the
discarded half.

<Widget type="quiz" id="com.github.richbai90.stats.13-wiener.quiz_orthogonality" />

<Widget type="quiz" id="com.github.richbai90.stats.13-wiener.quiz_causal" />

## What carries forward

The Wiener filter is the structured inverse of an inverse problem: recover
a buried signal with an estimator whose quality is limited by the noise
spectrum, the same wall that
[Lesson 1](/course/stats/observation-model) called precision. Module 3
will push this wall into explicit ill-posedness, where no filter, however
clever, divides its way out. Between here and there, Lessons 15–16 rebuild
the same optimum recursively, sample by sample, as the Kalman filter.

<Widget type="flashcard" id="com.github.richbai90.stats.13-wiener.card_normal" />

<Widget type="flashcard" id="com.github.richbai90.stats.13-wiener.card_snr" />

## Teach it back

The orthogonality principle is the load-bearing idea of all linear
estimation, from the LMMSE of Lesson 7 to the Kalman gain ahead. Teach
it, and the exact price of causality, before moving on.

<Widget type="teach" id="com.github.richbai90.stats.13-wiener.teach" />
