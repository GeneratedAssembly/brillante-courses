---
title: Random Processes
description: Wide-sense stationarity, autocorrelation, power spectra, and the Toeplitz covariance that turns physics into matrix structure. After Hayes, chapter 3.
order: 10
section: module-2
---

# Random Processes

Module 1 took the measurement vector $\mathbf{y}$ as given: fixed length, a
covariance you could write down by hand. Physical signals are not vectors of
numbers; they are **random processes**: random functions of time, indexed
over an unbounded clock. This lesson builds the bridge from physics to
matrices in two steps. First the second-order description of a process:
autocorrelation in time, power spectrum in frequency, tied together by
Wiener–Khinchin. Then the matrix consequence: sample a stationary process
into a block and the covariance is **Toeplitz**, constant along diagonals,
determined by one function of one integer.

The master model of [Lesson 1](/course/stats/observation-model) still governs
everything: $\mathbf{y} = \mathbf{h}(\boldsymbol\theta) + \mathbf{n}$. What
changes in Module 2 is the texture of $\mathbf{h}$ and $\mathbf{n}$. Instead
of a generic matrix and generic noise, both acquire structure inherited from
the physics of stationary processes, and structure is what algorithms feed
on.

## Wide-sense stationarity

A random process $x(n)$ is a random variable at every time $n$; its full
description is the joint distribution of $(x(n_0), x(n_1), \ldots)$, which no
physical dataset can ever pin down. Estimation needs only the second-order
layer, and the cleanest processes on that layer are **wide-sense stationary**
(WSS): the mean is constant in time and the autocorrelation depends only on
the separation between the two times.

<Widget type="math" id="com.github.richbai90.stats.10-random-processes.ac" />

WSS is a modeling decision, not a law of nature. Machinery heating up breaks
it; a sensor sitting at thermal equilibrium satisfies it. When it holds, one
function $r_x(k)$ carries all of the second-order physics: the power
($r_x(0)$), the memory (how fast $r_x(k)$ decays), and the oscillation (where
it rings).

<Widget type="quiz" id="com.github.richbai90.stats.10-random-processes.quiz_wss" />

## The power spectrum

The autocorrelation has a frequency-domain twin. The Wiener–Khinchin theorem
says the **power spectral density** is the discrete-time Fourier transform of
the autocorrelation, and the transform runs both ways; the two descriptions
are exactly equivalent:

<Widget type="math" id="com.github.richbai90.stats.10-random-processes.wk" />

$S_x(f)$ answers the engineering question directly: how is the power of the
process distributed over frequency? White noise has $S_x(f) = \sigma^2$, the
same power at every frequency; a resonator concentrates its power near a
natural frequency. The interactive below sweeps an AR(1) process (a
first-order all-pole model, introduced properly in the next lesson) with
$x(n) = p\,x(n-1) + w(n)$, plotted on a compressed square-root scale so the
shape stays visible as the pole approaches the unit circle.

<Widget type="interactive" id="com.github.richbai90.stats.10-random-processes.inter_psd" />

Read the sweep: as $p$ grows toward $1$, the spectrum concentrates its power
in a band around $f = 0$ and the peak sharpens without bound. Two facts
constrain every PSD: it is nonnegative, and it integrates to the total power,
$\int_{-1/2}^{1/2} S_x(f)\,\mathrm{d}f = r_x(0)$. The time picture and the
frequency picture allocate the same budget.

## Spectral factorization

For rational processes the PSD takes a form built from a filter, and the
**minimum-phase** factorization of that form is the algebra behind most of
Module 2:

<Widget type="math" id="com.github.richbai90.stats.10-random-processes.factorization" />

The fraction $B/A$ is the **shaping filter**: feed it white noise and the
output statistics are exactly the process you are modeling. Its poles and
zeros all sit inside the unit circle, which makes the factor stable and
causally invertible; the inverse is the **whitening filter** that turns the
process back into white noise. A worked instance: $S_x(f) = \tfrac{5}{4} +
\cos(2\pi f)$ factors as $\left|1 + \tfrac{1}{2}e^{-j2\pi f}\right|^2$. The
factorization shows up three times in this module: as AR modeling (Lesson
11), inside the causal Wiener filter (Lesson 13), and as the innovations
representation of state-space models (Lesson 15).

## The Toeplitz bridge

Now the matrix consequence, the one the module title points at. Take $N$
consecutive samples of a WSS process and form the covariance matrix:

<Widget type="math" id="com.github.richbai90.stats.10-random-processes.toeplitz" />

The matrix is **Toeplitz**: constant along its diagonals, symmetric, fully
determined by the $N$ values $r_x(0), \ldots, r_x(N-1)$ instead of
$N^2$ entries. This is how physics becomes matrix structure: stationarity
in time is exactly Toeplitz in the sample index. Two things you already own
now become matrix questions:

- [Lesson 7](/course/stats/bayes-map) priced the best linear estimator as the
  solution of one linear system whose matrix is $\mathbf{R}_x$. Toeplitz
  structure lets the Levinson–Durbin recursion (Lesson 12) run that solve in
  $\mathcal{O}(N^2)$ operations instead of $\mathcal{O}(N^3)$.
- Identifiability and precision from
  [Lesson 1](/course/stats/observation-model) reappear as conditioning: a
  sharply peaked spectrum makes $\mathbf{R}_x$ ill-conditioned, and
  ill-conditioning is where estimation precision goes to die.

<Widget type="quiz" id="com.github.richbai90.stats.10-random-processes.quiz_toeplitz" />

## Where Module 2 goes

The rest of the module climbs one ladder. Lesson 11 turns a physical
response into a rational model (ARMA, Padé, Prony). Lesson 12 runs the
Toeplitz recursion and its lattice form. Lesson 13 solves the optimum linear
filtering problem, Wiener's normal equations. Lesson 14 estimates spectra,
where resolution meets its structural limits. Lessons 15–16 re-derive the
same machinery in state-space form and meet the Kalman filter, which, you
will find, is the Gaussian–Gaussian conjugacy of
[Lesson 6](/course/stats/bayes-mmse) run recursively in time.

<Widget type="flashcard" id="com.github.richbai90.stats.10-random-processes.card_wss" />

<Widget type="flashcard" id="com.github.richbai90.stats.10-random-processes.card_psd" />

## Teach it back

Every algorithm in Module 2 feeds on the structure this lesson built.
Teach the WSS pair of pictures and the Toeplitz bridge before climbing
the ladder.

<Widget type="teach" id="com.github.richbai90.stats.10-random-processes.teach" />
