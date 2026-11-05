---
title: Iterative Grating Design
description: Bidirectional (Gerchberg–Saxton) algorithms, simulated annealing, and genetic algorithms — the three optimizers the book benchmarks on one 64 × 64 fanout.
order: 11
section: design
---

## The counting argument that makes it possible

The 64 × 64 fanout example has 4096 pixels: 4096 amplitudes and 4096 phases in
the unit cell, and the same in its Fourier plane — but a transform gives
8192 equations. **Know the amplitude in both planes and the phases in neither,
and the system is still determined** (Gerchberg & Saxton): 8192 unknowns,
8192 equations. The design problem is exactly to exploit that.

## Bidirectional algorithms (error reduction)

The loop alternates constraints in the two domains:

<Widget type="stepper" id="com.github.richbai90.diffractive.iter.step-gs" />

Mathematically (Eqs. 5.14–5.17): start from a random phase-only cell
$f^1 = e^{i\varphi^1}$; forward-transform $F^1 = \mathrm{FFT}[f^1]$; **replace
the computed amplitudes with the target amplitudes, keep the computed phases**;
inverse-transform; re-quantize; repeat. The figure of merit is the mean-square
error (Eq. 5.18):

<Widget type="math" id="com.github.richbai90.diffractive.iter.math-mse" />

On the 64 × 64 fanout: **MSE crashes from 8.2 to 0.87 within 12 iterations,
efficiency 85%** — seconds of computation on trivial hardware.

<Widget type="quiz" id="com.github.richbai90.diffractive.iter.quiz-gs" />

## The blind prospector: local minima

A 4096-dimensional solution space contoured like a mountain range; the
algorithm can only walk downhill.

<Widget type="flashcard" id="com.github.richbai90.diffractive.iter.card-prospector" />

The bidirectional result is *the best in whichever valley the random start
landed in* — "How will you know when you have found the best solution? You
won't. But for many applications the results are completely adequate."
Craggy merit surfaces (designs very sensitive to small changes) trap it in
little nooks. Enter the stochastic searchers.

## Simulated annealing

A **unidirectional** algorithm (forward transform only) modeled on
crystallizing metals: molten metal cooled *slowly* forms large, strong
crystals; quenched, it freezes into brittle disorder. The design analogue:
perturb cell phases randomly; **always accept moves that lower the MSE;
accept uphill moves with probability controlled by a temperature-like
variable $t$ that decays with iteration** (Eq. 5.19's random start, then the
accept/reject test $p < t_k$).

<Widget type="quiz" id="com.github.richbai90.diffractive.iter.quiz-anneal" />

Prospector version: give him enormous legs — at first he leaps anywhere,
exploring whole valleys; as "cooling" proceeds his leaps shorten and uphill
acceptance dies, and he descends like the deterministic method — but now the
answer is **not** determined by where he started. On the 64 × 64 example:
minimum in ~2000 iterations, **MSE 0.12, efficiency 76%** — 10× the
computation of bidirectional for a 7× better fit (the book: uniformity to the
target is the true figure of merit here, so annealing wins despite lower
efficiency). Rules of thumb: very slow cooling has a *mathematical proof* of
finding the global minimum; start with $t = 0$ and you have merely built a
deterministic hill-climber. Practical ceiling on the book's 500-MHz PC:
~512 × 512 variables (designs to 2048 × 2048 = 4,194,304 variables were done).

## Genetic algorithms

Same unidirectional frame, but a **population** of estimates instead of one.
Cell variables are concatenated into a **chromosome** (Eq. 5.20 keeps the four
phase levels); each generation: transform every member, rank by MSE
($R_{k,l} = \mathrm{MSE}(F^{k,l})$, Eq. 5.21), select parents **at random with
probability weighted by rank** (worst member < 1% chance of breeding, best
33%), **cross over** at random breakpoints — several breakpoints converge
faster, but the advantage dies once breakpoints exceed ~5–10% of the variables
— and **mutate** a few random genes to fight inbreeding.

<Widget type="flashcard" id="com.github.richbai90.diffractive.iter.card-ga" />

Prospector version: a scattered *team* of blind prospectors who each leap
toward whoever reports being lowest — interacting, stochastic, goal-directed.
Result on the same problem: minimum in ~400–800 generations, **MSE 0.11,
efficiency 76%**, just under $10^{10}$ computations — statistically
indistinguishable from annealing on this problem. Tuning: large populations
sample better; a flat ranking function keeps poor traits alive; too much
mutation slows convergence, none causes premature stagnation.

## The scoreboard

| Method | MSE | Efficiency | Work | Guarantee |
|---|---|---|---|---|
| Direct inversion | 8.2 | 46% | one FFT | none |
| Bidirectional | 0.87 | 85% | ~12 iterations, ~10⁶ ops | best in starting valley |
| Simulated annealing | 0.12 | 76% | ~2000 iterations, <10¹⁰ ops | global min only with infinitely slow cooling |
| Genetic algorithm | 0.11 | 76% | ~400–800 generations, <10¹⁰ ops | a minimum, consistently |

The book's closing design rule: **choose the algorithm by the criterion of
providing an acceptable design using the simplest technique** — Dammann or
direct inversion for simple outputs, deterministic bidirectional for complex
invertible systems, stochastic methods for the hardest patterns. (One more
data point: a bidirectional beam shaper — Gaussian to uniform square, a
*non-periodic* problem solved with Fresnel transforms — had 250,000+
variables yet converged in under an hour, because its merit surface happens to
be smooth with a single general solution.)

<Widget type="quiz" id="com.github.richbai90.diffractive.iter.quiz-score" />

<Widget type="quiz" id="com.github.richbai90.diffractive.iter.quiz-rule" />

<Widget type="flashcard" id="com.github.richbai90.diffractive.iter.card-taxonomy" />
