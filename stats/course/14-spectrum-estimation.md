---
title: Spectrum Estimation
description: Periodogram, Welch averaging, and the data-adaptive methods (MVDR and MUSIC), where resolution meets its structural limits. After Hayes, chapter 8.
order: 14
section: module-2
---

# Spectrum Estimation

Everything so far estimated *parameters*: a mean, a variance, $p + q + 1$
filter coefficients. Spectrum estimation targets a **function**, $S_x(f)$,
from a single finite record, and the moment the target is a function, the
identifiability and precision disciplines of
[Lesson 1](/course/stats/observation-model) stop being a formality. There
are infinitely many spectra consistent with short records; every method in
this lesson is a different truce between bias (how much structure you
impose) and variance (how much the data flaps).

## The periodogram

<Widget type="math" id="com.github.richbai90.stats.14-spectrum-estimation.periodogram" />

The scaled squared magnitude of the DFT. Its virtue is that it makes no
assumptions; its flaw is fatal in small samples: it is **not consistent**.
Averaging more data refines the frequency grid, but the value at each grid
point keeps flapping with variance near the squared PSD; a longer record
buys resolution, not stability. [Lesson 3](/course/stats/crlb) taught you
to ask for the variance of an estimator; here the variance simply refuses
to fall.

## Averaging: Bartlett and Welch

The classical truce is averaging. Split the record into $K$ segments of
length $L$, periodogram each, average:

<Widget type="math" id="com.github.richbai90.stats.14-spectrum-estimation.welch" />

Variance falls like $1/K$; resolution falls with it, from $1/N$ to the
segment width $1/L$. The window $w$ (with normalization $U$) tames the
leakage at the price of widening the main lobe. This is the bias-variance
ledger of [Lesson 2](/course/stats/mvue) in the frequency domain, and it
is unavoidable: you may choose where to sit on the ledger, not whether it
exists.

<Widget type="quiz" id="com.github.richbai90.stats.14-spectrum-estimation.quiz_averaging" />

## Data-adaptive spectra: MVDR

The periodogram weights every frequency band independently of the data.
Capon's minimum-variance distortionless response inverts the measured
covariance and lets the *data* design the band:

<Widget type="math" id="com.github.richbai90.stats.14-spectrum-estimation.mvdr" />

The scan vector $\mathbf{a}(f)$ looks at the record through a filter that
passes frequency $f$ with unit gain while minimizing output power; the
inverse covariance is what makes the band aware of everything else in the
spectrum. The result resolves components the periodogram blends, paid for
with the assumption that the covariance is estimable from the record:
short or ill-conditioned records break it exactly where it is supposed to
help.

## Subspace methods: MUSIC

When the physics says *a few lines in white noise*, the covariance is
roughly low-rank plus a scaled identity, and its eigenvectors split into
a signal subspace and a noise subspace. MUSIC scans the noise subspace
for its zeros:

<Widget type="math" id="com.github.richbai90.stats.14-spectrum-estimation.music" />

At a true line frequency the steering vector is orthogonal to every noise
eigenvector, the denominator vanishes, and the pseudo-spectrum spikes,
resolution far beyond $1/N$. The fine print is the model bet:
[Lesson 1](/course/stats/observation-model)'s identifiability discipline
applies verbatim. If the true spectrum is *not* a few lines in white
noise, the subspace split is fiction and the super-resolution is
confident nonsense.

<Widget type="quiz" id="com.github.richbai90.stats.14-spectrum-estimation.quiz_resolution" />

## The inverse-problem preview

Periodogram, Welch, MVDR, MUSIC: one target, four positions on the
assumption-to-variance dial. What the dial cannot do is escape finiteness:
from $N$ numbers you will not recover a general function of a continuum.
That is an ill-posed inverse problem, and Module 3 is where this course
stops dodging it: explicit models, explicit penalties, and the mathematics
of making underdetermined questions answerable.

<Widget type="flashcard" id="com.github.richbai90.stats.14-spectrum-estimation.card_periodogram" />

<Widget type="flashcard" id="com.github.richbai90.stats.14-spectrum-estimation.card_highres" />
