---
title: Fanout Grating Design
description: 1-to-N wavefront mapping — the two design knobs (period and unit cell), the 1 × 3 grating you can solve by hand, Dammann's equations, and the direct-inversion method that fails informatively.
order: 10
section: design
---

Chapter 4 mapped one ray to one ray — a DOE mimicking a lens. This lesson and
the next cover **1-to-N mapping**: splitting a wavefront into an array of
beams with controlled powers. Everything rests on the two facts established in
[What Is a DOE](01-what-is-a-doe.md):

1. **The grating period alone controls the angular separation and orientation
   of the orders** ($\sin\theta_m = m\lambda/\Lambda$).
2. **The structure within the unit cell alone controls the relative amplitude
   and phase of the orders.**

Design therefore splits into two manageable tasks: pick the period from the
desired spot angles, then build the unit cell to distribute power the way you
want.

## A 1 × 3 grating by hand

Start from the binary π grating of the foundations lessons: 40.5% in each of
±1, zero in the 0th — a 1 × 2 splitter at 81%. To get *three* equal beams you
must feed the zero order, and there are two knobs.

**Knob 1: the duty cycle.** With $b/\Lambda \ne 1/2$, the cancellation breaks
and the zero order appears:

<Widget type="interactive" id="com.github.richbai90.diffractive.fanout.int-duty0" />

<Widget type="interactive" id="com.github.richbai90.diffractive.fanout.int-duty1" />

Slide to $b/\Lambda = 0.265$ and the two curves cross at **22% each**: orders
−1, 0, +1 equal — a 1 × 3 beamsplitter at $3 \times 22\% = 66\%$ efficiency
(the other 34% leaks to the remaining orders).

**Knob 2: the phase depth.** Keep 50% duty and make the etch *shallower* than
π. Equalizing $\eta_0 = \eta_1$ solves to $\phi = 2\arctan(\pi/2) = 0.64\pi$,
and each of the three orders carries **28.8% — an 86% efficient 1 × 3
grating**, with even orders still nulled by the symmetry.

<Widget type="quiz" id="com.github.richbai90.diffractive.fanout.quiz-knobs" />

The takeaway is not the numbers but the freedom: unit-cell structure steers
power among orders **without moving the orders at all**. (Phase depth is a
good variable only in simple binary designs; in general it is fixed by the
material and wavelength.)

## Dammann gratings and the wall

Dammann's method for 1 × N: assume binary π depth, put several transition
points in each period, and demand the zero order plus the first $N$ orders all
have equal intensity — **N nonlinear equations in N unknowns** (the transition
locations). Elegant for small N, "daunting" beyond, and it does not extend to
2-D or multilevel structures. Industrial fanouts range from the **1 × 3
elements in compact-disk heads** to 2-D illuminators with **270,000 orders** —
far past anything analytic. You need an algorithm.

## How many variables can you afford?

Encode the unit cell as pixels of the smallest fabricable feature $\ell$ in a
beam of size $L$: the design space is the **space–bandwidth product**
(Eq. 5.8)

<Widget type="math" id="com.github.richbai90.diffractive.fanout.math-sbwp" />

A 10-mm beam at $\lambda = 1\,\mu$m with 1-µm features is $10^8$ variables —
information capacity, but also a computational threat. The book's three
encodings, in rising order of freedom:

- **Transition points** (Dammann style): move the edges of rectangles; a
  25-feature 2-D cell is 8 variables.
- **Trapezoids**: non-rectilinear edges add design freedom (16 more variables
  in the same cell) — and mask software already accepts trapezoids.
- **Pixel arrays** (most common): each pixel gets one of $N$ preset phase
  depths; rectangular pixels map straight to mask data and FFTs.

<Widget type="flashcard" id="com.github.richbai90.diffractive.fanout.card-encoding" />

## Direct inversion — and why it fails

The naive route: take the target spot pattern, assign each spot its known
amplitude $A_{m,n} = \sqrt{I_{m,n}}$ and a **random phase**, inverse-FFT, then
truncate: force amplitude to 1 and quantize phase to $N$ levels
$\{0, 2\pi/N, \dots\}$.

<Widget type="stepper" id="com.github.richbai90.diffractive.fanout.step-inversion" />

Worked example (the one every later algorithm reuses): fanout spots separated
0.5° at $\lambda = 633$ nm ⇒ $\Lambda = 0.633/\sin 0.5° = 72.5\,\mu$m; with
1-µm minimum features, a 64 × 64 FFT grid gives 1.133-µm pixels.

Playback of the inverted design: **MSE = 8.2, efficiency 46%** — noisy, spots
buried in sidelobes. The diagnosis matters more than the failure: the damage
comes mostly from **forcing the amplitude to unity** (a dramatic information
loss), then from phase quantization; 8+ levels restore fidelity, 2 levels are
very noisy. Randomizing the target phases was itself a trick — uniform phases
would concentrate all the amplitude in the cell's center. Which target phases
*minimize* the amplitude modulation? **That question is the entire subject of
[Iterative Design](11-iterative-design.md).**

<Widget type="quiz" id="com.github.richbai90.diffractive.fanout.quiz-invert" />

<Widget type="quiz" id="com.github.richbai90.diffractive.fanout.quiz-period" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.fanout.card-facts" />
