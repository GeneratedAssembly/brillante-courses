---
title: Signal Modeling
description: From measured response to rational model; ARMA structure, the Padé exact fit, the Prony least-squares fit, and the all-pole spectrum. After Hayes, chapter 4.
order: 11
section: module-2
---

# Signal Modeling

Module 1 measured static parameters; physical systems have **dynamics**. A
vibrating structure, a communication channel, a blurred lens: each maps its
input to its output through a filter with memory. This lesson is where the
forward operator of [Lesson 1](/course/stats/observation-model) acquires the
shape it keeps for the rest of the course: $\mathbf{h}$ becomes a rational
transfer function $H(z) = B(z)/A(z)$, a handful of poles and zeros that
encode the physics, and the structured matrix built from those coefficients
is what Modules 3–5 will invert.

The plan of attack is inverse: you observe the response and *fit* the
rational model to it. Two classical fitting recipes, Padé and Prony,
solve the same equations with different demands on the data.

## The rational model classes

<Widget type="math" id="com.github.richbai90.stats.11-signal-modeling.arma" />

The three classes differ in what they put where:

- **AR** (autoregressive): all pole, $B(z) = b_0$. Resonances and ringing
  come from poles near the unit circle. The workhorse of spectral modeling.
- **MA** (moving average): all zero, $A(z) = 1$. Notches and nulls come from
  zeros on or near the unit circle.
- **ARMA**: both. A rational model with $p$ poles and $q$ zeros needs
  $p + q + 1$ coefficients, a physics-compression of an arbitrary impulse
  response.

This $B/A$ is the minimum-phase factor of
[Lesson 10](/course/stats/random-processes): the shaping filter whose output
statistics are the process, and whose inverse whitens it.

## Padé: exactness first

Cross-multiplying $H(z) A(z) = B(z)$ and matching coefficients produces one
family of equations, and one of them is the whole game:

<Widget type="math" id="com.github.richbai90.stats.11-signal-modeling.pade" />

Beyond lag $q$ the numerator cannot contribute: the impulse response
satisfies the homogeneous recursion of the denominator alone. The **Padé
approximation** takes $p + q + 1$ samples of $h(n)$ as exact, solves the $p$
tail equations for the denominator, then reads the numerator off the first
$q + 1$ coefficients. Exact, and therefore brittle: one noisy sample poisons
the whole fit.

## Prony: the tail by least squares

Prony keeps the Padé equations but refuses to trust any single one of them.
Every available sample past lag $q$ contributes one equation, and the
denominator is the least-squares solution:

<Widget type="stepper" id="com.github.richbai90.stats.11-signal-modeling.stepper_prony" />

The trade is worth internalizing: Prony gives up exactness at low lags to
buy robustness over the whole tail. With noiseless data from a true rational
system and enough samples, the LS solution converges to the Padé answer.
With noisy data it is the only one of the two that works, and
[Lesson 1](/course/stats/observation-model) told you why: more equations
per unknown is precision, not decoration.

## The all-pole spectrum

Why spectral modelers lean AR: the pole structure *is* the spectrum. With
$B(z) = b_0$ the PSD of
[Lesson 10](/course/stats/random-processes) closes into one formula:

<Widget type="math" id="com.github.richbai90.stats.11-signal-modeling.ar_spectrum" />

Each pole pair lifts the spectrum near its frequency; the farther the pole
sits from the unit circle, the wider the lift. The interactive in
[Lesson 10](/course/stats/random-processes) was exactly this formula for
$p = 1$. The denominator coefficients determine the spectrum *shape* and
$\sigma_w^2$ only sets its scale; that is why the Yule–Walker system of
the next lesson can read the model off the autocorrelation alone.

<Widget type="quiz" id="com.github.richbai90.stats.11-signal-modeling.quiz_model" />

<Widget type="quiz" id="com.github.richbai90.stats.11-signal-modeling.quiz_prony" />

## From model to operator

Fit the rational model and you have rebuilt the physics: $A$ and $B$ are
the forward operator in filter form. Everything downstream consumes this
object: Wiener filtering (Lesson 13), state-space models (Lesson 15), the
structured inverse problems of Module 3. The next lesson shows
that for the all-pole case the fit can even be computed recursively, one
order at a time.

<Widget type="flashcard" id="com.github.richbai90.stats.11-signal-modeling.card_rational" />

<Widget type="flashcard" id="com.github.richbai90.stats.11-signal-modeling.card_pade_prony" />

## Teach it back

The rational model is the shape the forward operator keeps for the rest
of the course. Teach the Padé–Prony trade and the all-pole spectrum
before the recursion lesson consumes them.

<Widget type="teach" id="com.github.richbai90.stats.11-signal-modeling.teach" />
