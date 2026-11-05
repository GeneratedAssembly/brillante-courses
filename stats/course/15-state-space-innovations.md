---
title: State-Space Models and the Innovations
description: The (A, B, C) triple, the Lyapunov covariance ledger, and the innovations process, the whitening view that sets up the Kalman filter. After Kailath, Sayed and Hassibi.
order: 15
section: module-2
---

# State-Space Models and the Innovations

Lessons 10–14 described signals by their *external* behavior: autocorrelations,
spectra, transfer functions. The state-space view describes them by their
*internal* machinery: a memory variable evolving in time, a sensor reading
part of it. Same physics, different coordinates; the extra coordinates
are exactly what the Kalman filter will consume. The master model survives
one more translation:
$\mathbf{y} = \mathbf{h}(\boldsymbol\theta) + \mathbf{n}$ becomes a pair of
equations, one for the hidden state and one for the measurement.

## The triple

<Widget type="math" id="com.github.richbai90.stats.15-state-space-innovations.state_space" />

$\mathbf{A}$ is the dynamics: it carries memory, and its eigenvalues are the
poles. Stability means all of them sit inside the unit circle, exactly
the minimum-phase condition of
[Lesson 10](/course/stats/random-processes). $\mathbf{B}$ injects the
driving noise $\mathbf{u}$, white with covariance $\mathbf{Q}$.
$\mathbf{C}$ is the sensor: what the outside world sees of the state, plus
the measurement noise $\mathbf{v}$ with covariance $\mathbf{R}$. A
vibrating beam has states for mode amplitudes and velocities; a tracking
radar has states for position and velocity; the sensor measures only part.

## The covariance ledger

Run the unobserved process long enough and its covariance reaches a
steady state. Balance inflow against decay:

<Widget type="math" id="com.github.richbai90.stats.15-state-space-innovations.lyapunov" />

The **Lyapunov equation** is the state-space ledger: each step adds
$\mathbf{B}\mathbf{Q}\mathbf{B}^{\mathsf{T}}$ of fresh uncertainty and
$\mathbf{A}\boldsymbol\Pi\mathbf{A}^{\mathsf{T}}$ is what survives of the
old. This is the same power bookkeeping as $r_x(0)$ in
[Lesson 10](/course/stats/random-processes), kept in matrix form, and for
a scalar process it closes to the familiar
$\Pi = q\,/\,(1 - a^2)$, the variance of an AR(1) process.

## Two grammars, one filter

Eliminate the state and the triple collapses into the rational filter of
[Lesson 11](/course/stats/signal-modeling):

<Widget type="math" id="com.github.richbai90.stats.15-state-space-innovations.transfer" />

The pulse transfer function is a rational $H(z)$ like any other, so the
state-space view is *equivalent* to the input-output view, no more and no
less accurate. What the realization adds is structure the external view
hides: which state combinations the input can reach (**controllability**),
which the sensor can see (**observability**), and whether the realization
is minimal. The same filter has infinitely many realizations; only the
minimal ones use no more states than the physics demands. Lesson 18 works
these properties by hand.

## The innovations

Now the conceptual center of the module. Define the **one-step predictor**
$\hat{\mathbf{y}}(n \mid n - 1)$, the best estimate of the next
observation given all previous ones, and form the residual:

<Widget type="math" id="com.github.richbai90.stats.15-state-space-innovations.innovations" />

The residual is **white**. If it were not, the leftover correlation would
be usable information and $\hat{\mathbf{y}}$ would not be optimal, the same
orthogonality principle as the Wiener filter of
[Lesson 13](/course/stats/wiener), one sample at a time. Each innovation
is literally the *new information* in the new sample: everything
predictable has been subtracted away, and what remains cannot be said
twice.

This is a re-derivation, in new clothes, of three earlier ideas. The
innovations are the output of a whitening filter, the causal inverse of
[Lesson 10](/course/stats/random-processes)'s spectral factorization. For
a pure AR process the innovations are the driving noise itself, the
residual of
[Lesson 11](/course/stats/signal-modeling)'s tail equation. And their
variance is the $\sigma_e^2$ that normalized the causal Wiener filter in
[Lesson 13](/course/stats/wiener).

<Widget type="quiz" id="com.github.richbai90.stats.15-state-space-innovations.quiz_innovations" />

<Widget type="quiz" id="com.github.richbai90.stats.15-state-space-innovations.quiz_equivalence" />

## Ready for Kalman

The innovations representation converts filtering into bookkeeping:
estimate the state by predicting it, subtract what the new observation
reveals, and scale the correction by how much *new* information arrived.
That recursion, one predict step and one correct step per sample, is the
Kalman filter, and
[Lesson 16](/course/stats/kalman) derives it as nothing more than the
Gaussian conjugacy of [Lesson 6](/course/stats/bayes-mmse) run
recursively in time.

<Widget type="flashcard" id="com.github.richbai90.stats.15-state-space-innovations.card_state_space" />

<Widget type="flashcard" id="com.github.richbai90.stats.15-state-space-innovations.card_innovations" />

## Teach it back

The innovations view is what the Kalman filter consumes. Teach the
triple, the Lyapunov ledger, and why the residual is white before the
recursion lesson.

<Widget type="teach" id="com.github.richbai90.stats.15-state-space-innovations.teach" />
