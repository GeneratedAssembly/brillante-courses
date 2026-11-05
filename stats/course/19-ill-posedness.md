---
title: When Inversion Fails
description: Discretized inverse problems, the SVD lens, condition numbers, and why small singular values amplify noise. After Boyd and Vandenberghe, appendix C and chapter 6.
order: 19
section: module-3
---

# When Inversion Fails

[Lesson 7](/course/stats/bayes-map#the-coincidence-that-opens-module-3) ended
with a coincidence: the Bayesian MAP estimator with a Gaussian prior is a
penalized least-squares problem, identical in form to the deterministic
shrinking of an ill-conditioned inverse. Module 3 cashes that coincidence in.
The master model is still $\mathbf{y} = \mathbf{h}(\boldsymbol\theta) +
\mathbf{n}$, but now $\mathbf{h}$ is a big matrix $\mathbf{H}$ built from
physical discretization, and the question is no longer the bias of an
estimator but the stability of an inverse. After Boyd and Vandenberghe, this
module treats estimation as optimization, and optimization begins with an
honest autopsy of the forward operator.

## From physics to a matrix

A spectrometer integrates a continuous spectrum against a kernel. A camera
blurs a scene with a point-spread function. A seismometer convolves the
subsurface with a wavelet. Sample the unknown on a grid of $N$ points, record
$N$ measurements, and each physical operation becomes a linear map:

<Widget type="math" id="com.github.richbai90.stats.19-ill-posedness.discretize" />

The structure is inherited from physics: a shift-invariant kernel produces a
Toeplitz matrix (constant diagonals, exactly the covariance structure of
[Lesson 10](/course/stats/random-processes)), and periodic boundaries make it
circulant, diagonalized by the DFT. This is the bridge Module 2 built: the
same $\mathbf{H}$ that models the forward physics dictates every cost of
running the inverse.

## The SVD lens

Every matrix, however it was born, admits a singular value decomposition, and
the SVD is the complete diagnostic of an inverse:

<Widget type="math" id="com.github.richbai90.stats.19-ill-posedness.svd" />

In the basis of singular vectors, the forward map is diagonal: stretch
direction $i$ by $\sigma_i$, and invert by dividing. Components of the signal
aligned with small singular values are barely observed (they produce almost
no output), and recovering them demands dividing by almost nothing.

## The condition number

<Widget type="math" id="com.github.richbai90.stats.19-ill-posedness.cond" />

The bound is the contract of inversion: relative error in the estimate is at
most $\kappa$ times relative error in the data. A well-conditioned operator
faithfully transmits noise; an ill-conditioned one is a lever that turns
millivolts of sensor noise into volts of wrong answer.

<Widget type="quiz" id="com.github.richbai90.stats.19-ill-posedness.quiz_svdfail" />

## Noise amplification, up close

The pseudo-inverse divides each singular-vector component of the observation
by $\sigma_i$. Noise rides along uninvited, so the noise gain in direction $i$
is exactly $1/\sigma_i$. Drag the smallest observed singular value toward
zero and watch the lever:

<Widget type="interactive" id="com.github.richbai90.stats.19-ill-posedness.inter_amp" />

<Widget type="quiz" id="com.github.richbai90.stats.19-ill-posedness.quiz_amplify" />

## Where the noise floor comes from

The noise $\mathbf{n}$ is not an abstraction; it is the photon-counting
variance of [Lesson 5](/course/stats/mle-poisson#photon-counting), the
quantization of an ADC, the thermal hiss of a preamp. Ill-posedness alone
does not ruin an inverse problem; ill-posedness times a noise floor does.
A perfectly noiseless measurement of $\mathbf{y} = \mathbf{H}\mathbf{x}$ can
be inverted to any accuracy the grid allows; the same problem with one part
in $10^{4}$ of noise on the smallest singular direction is already
unrecoverable. This is why [Lesson 14](/course/stats/spectrum-estimation#the-inverse-problem-preview)
called resolution an inverse-problem preview: the periodogram divides by
powers of a blurred kernel, and MUSIC refuses to invert the noise subspace
at all.

Two escape routes exist. Either reduce the noise floor (longer exposures,
cooled sensors, the shot-noise budget of Lesson 5) or stop trying to
invert the badly observed directions, which means changing the question from
*invert $\mathbf{H}$* to *estimate $\mathbf{x}$ with a prior*. That choice is
the rest of this module.

## What carries forward

The SVD told us where inversion dies: in the small singular values. The next
lesson builds the vocabulary for the fix (convex sets, cones, and
projections), and from there penalties (Lesson 21) turn the ill-posed
inversion back into the well-posed estimation that
[Lesson 7](/course/stats/bayes-map#lmmse-the-best-linear-rule) already
glimpsed.

<Widget type="flashcard" id="com.github.richbai90.stats.19-ill-posedness.card_svd" />

<Widget type="flashcard" id="com.github.richbai90.stats.19-ill-posedness.card_cond" />

## Teach it back

Everything in Module 3 answers the autopsy in this lesson. Teach the SVD
lens, the condition number, and the two escape routes before the
geometry arrives.

<Widget type="teach" id="com.github.richbai90.stats.19-ill-posedness.teach" />
