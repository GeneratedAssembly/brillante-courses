---
title: The Kalman Filter
description: The Kalman filter as recursive innovations estimation; predictor–corrector, the RTS smoother, and Gaussian conjugacy run in time. After Kailath, Sayed and Hassibi.
order: 16
section: module-2
---

# The Kalman Filter

Module 1 solved the Gaussian–Gaussian problem once:
[Lesson 6](/course/stats/bayes-mmse) took a Gaussian prior and one Gaussian
observation and produced a Gaussian posterior by adding precisions. The
Kalman filter is that single piece of algebra, run recursively in time:
today's posterior becomes tomorrow's prior, the dynamics inflate the
uncertainty between observations, and each observation shrinks it again.
Nothing deeper is required, which is precisely Kailath's point. The
filter is not a new estimation theory; it is the innovations bookkeeping
of [Lesson 15](/course/stats/state-space-innovations) executed sample by
sample.

## Predict

Between observations the state propagates by the dynamics, and
uncertainty propagates with it:

<Widget type="math" id="com.github.richbai90.stats.16-kalman.predict" />

The covariance is the whole state of knowledge here: $\mathbf{P}(n \mid n
- 1)$ is what you would know about $x(n)$ *before* seeing $y(n)$, and the
$\mathbf{B}\mathbf{Q}\mathbf{B}^{\mathsf{T}}$ term is the fresh process
noise of [Lesson 15](/course/stats/state-space-innovations)'s Lyapunov
ledger, injected once per step.

## Correct

The new observation arrives through the sensor, $\mathbf{y}(n) =
\mathbf{C}\mathbf{x}(n) + \mathbf{v}(n)$. Its residual against the
prediction is the innovation $\mathbf{e}(n)$, and the correction is a
precision-weighted step along it:

<Widget type="math" id="com.github.richbai90.stats.16-kalman.gain" />

<Widget type="math" id="com.github.richbai90.stats.16-kalman.update" />

Read the gain with
[Lesson 6](/course/stats/bayes-mmse)'s eyes: $\mathbf{K}(n)$ is the
shrinkage weight $w$ with the roles swapped: trust the observation in
proportion to how uncertain the prediction is. A noisy sensor ($\mathbf{R}$
large) shrinks the gain toward zero; a wild, poorly modeled process
(large $\mathbf{P}$) pushes it toward full trust. The covariance update is
the same precision ledger in a different coat: predict inflates,
observation shrinks, forever.

## Lesson 6, run in time

<Widget type="stepper" id="com.github.richbai90.stats.16-kalman.stepper_scalar" />

The scalar walk-through makes the lineage impossible to miss: the
predict step manufactures the prior, the correct step is Gaussian
conjugacy verbatim, and recursion replaces re-derivation. This is the
structural view of the module: filter, whitener, and predictor are one
machine wearing three hats.

<Widget type="quiz" id="com.github.richbai90.stats.16-kalman.quiz_gain" />

## Smoothing: the future, used

Filtering is what real time allows. Offline, the future exists and should
be spent. The Rauch–Tung–Striebel smoother runs the Kalman filter forward
once, then walks backward, correcting each filtered estimate with what the
future revealed:

<Widget type="math" id="com.github.richbai90.stats.16-kalman.rts" />

The smoother gain $\mathbf{G}(n)$ scales the discrepancy between the
future's smoothed estimate and what the dynamics predicted from step $n$.
Variance decreases monotonically along the backward pass; smoothing uses
a superset of the filtered data, and no estimator that uses more
information does worse. The gap between $\mathbf{P}(n \mid n)$ and
$\mathbf{P}(n \mid N)$ is exactly the price of causality, the same price
the causal Wiener filter of [Lesson 13](/course/stats/wiener) paid in the
frequency domain.

<Widget type="quiz" id="com.github.richbai90.stats.16-kalman.quiz_smoothing" />

## Module 2 closes

The ladder is complete: physics became stationary structure
([Lesson 10](/course/stats/random-processes)), structure became rational
models ([Lesson 11](/course/stats/signal-modeling)), Toeplitz recursion
([Lesson 12](/course/stats/levinson-lattice)), optimum filtering
([Lesson 13](/course/stats/wiener)), spectra and their limits
([Lesson 14](/course/stats/spectrum-estimation)), state-space machinery
([Lesson 15](/course/stats/state-space-innovations)), and finally a
recursive Bayesian filter built from one Gaussian conjugacy step. Two
problem sets now fix it in place; then Module 3 takes the structured
operator $\mathbf{h}$ into the territory where inversions stop being
polite: ill-posedness, constraints, and regularization.

<Widget type="flashcard" id="com.github.richbai90.stats.16-kalman.card_kf" />

<Widget type="flashcard" id="com.github.richbai90.stats.16-kalman.card_rts" />

## Teach it back

Module 2's ladder ends here, and Module 5 rebuilds this filter without
Gaussianity. Teach the predict–correct recursion as Lesson 6 run in
time, then the ladder itself, before moving on.

<Widget type="teach" id="com.github.richbai90.stats.16-kalman.teach" />
