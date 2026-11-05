---
title: The Levinson Recursion
description: Solving the Yule–Walker system one order at a time; Levinson–Durbin, reflection coefficients, and the lattice filter. After Hayes, chapter 5.
order: 12
section: module-2
---

# The Levinson Recursion

Lesson 11 ended with the all-pole promise: the denominator coefficients
(the physics) are fully determined by the autocorrelation. This lesson pays
it off. The Yule–Walker equations turn $r_x(0), \ldots, r_x(p)$ into the
AR model, and the **Levinson–Durbin recursion** solves them by climbing
through model orders, reusing everything already computed. The intermediates
are not bookkeeping: the **reflection coefficients** that fall out are a
complete re-parameterization of the process, and they are exactly the
couplings of the **lattice filter**, the most numerically comfortable signal
processing structure ever built.

## The Yule–Walker system

Multiply the all-pole model of
[Lesson 11](/course/stats/signal-modeling) through by $x(n-i)$ and take
expectations. The driving noise decorrelates from the past, and what remains
is a Toeplitz system:

<Widget type="math" id="com.github.richbai90.stats.12-levinson-lattice.yw" />

A general solver needs $\mathcal{O}(p^3)$ operations for the $p \times p$
system, and learns nothing on the way. The matrix is Toeplitz, and
Toeplitz structure, as
[Lesson 10](/course/stats/random-processes) established, is exactly what
stationarity buys. Levinson–Durbin spends that structure.

## The recursion

<Widget type="stepper" id="com.github.richbai90.stats.12-levinson-lattice.stepper_levinson" />

The engine is the order recursion: solve order $m$ from order $m - 1$ plus
one new scalar measurement, $r_x(m)$. Total cost $\mathcal{O}(p^2)$ with
$\mathcal{O}(p)$ memory, and at every order you hold a complete, stable
model of that order, which is also how model order gets chosen in
practice: climb until the prediction-error power stops falling.

## Reflection coefficients

The single new number at each order has a name and a physical life of its
own:

<Widget type="math" id="com.github.richbai90.stats.12-levinson-lattice.reflection" />

$k_m$ measures how much the process extends beyond what order $m - 1$
already predicts, the mismatch between the extrapolated autocorrelation
and the measured one. In the wave interpretation (acoustics, geophysics,
optics) it is literally a reflection coefficient: the fraction of a wave
bounced at the interface between layers $m - 1$ and $m$. The update rule
folds the coefficient vector onto its own reversal:

<Widget type="math" id="com.github.richbai90.stats.12-levinson-lattice.order_recursion" />

The error update is the certification of the whole enterprise: as long as
$\mathcal{E}_m > 0$ at every order, every $|k_m| < 1$, and the AR
polynomial is minimum phase: stable, with a stable causal inverse. The
positivity you would demand of a covariance matrix arrives as a
one-per-order checkpoint inside the algorithm.

## The lattice filter

Rewrite the same recursion as a signal flow and you get the lattice: a
cascade of identical two-port stages, each taking a forward and a backward
prediction error and mixing them once:

<Widget type="math" id="com.github.richbai90.stats.12-levinson-lattice.lattice" />

$f_m$ predicts the next sample from the recent past; $b_m$ is the backward
prediction error, and its orthogonality properties are what make lattice
filters numerically robust and modular: order-adaptive by construction,
every stage bounded by $|k_m| < 1$, and the coefficient sequence $k_1,
\ldots, k_p$ parameterizes the process with stability built in.

<Widget type="quiz" id="com.github.richbai90.stats.12-levinson-lattice.quiz_structure" />

<Widget type="quiz" id="com.github.richbai90.stats.12-levinson-lattice.quiz_stability" />

## What carries forward

Two exports. First, the technique: Lesson 13's Wiener solve and Module 3's
structured inverses all price themselves against Toeplitz structure, and
Levinson–Durbin is the proof that the discount is real. Second, the
parameterization: when Lesson 15 re-derives estimation in state-space form,
the innovations view and the lattice view are two grammars for the same
whitening idea. Precision, identifiability, and
[Lesson 1](/course/stats/observation-model)'s discipline never left; they
are what the positivity checkpoint is *for*.

<Widget type="flashcard" id="com.github.richbai90.stats.12-levinson-lattice.card_levinson" />

<Widget type="flashcard" id="com.github.richbai90.stats.12-levinson-lattice.card_lattice" />
