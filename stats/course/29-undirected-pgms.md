---
title: Symmetric Neighborhoods
description: Markov random fields, pairwise potentials, Gibbs distributions, the Hammersley–Clifford theorem, and an image-prior example. After Bishop, section 8.3, and Barber, chapter 4.
order: 29
section: module-4
---

# Symmetric Neighborhoods

Some structure has no direction. Neighboring pixels agree or disagree; two
materials abut; spins align. Forcing a directed arrow between symmetric
relations manufactures a causality you do not have. A Markov random field
drops the arrows and keeps the neighborhoods: each variable is independent
of the rest given its immediate neighbors. After Bishop, section 8.3, and
Barber, chapter 4.

## Potentials, not conditionals

<Widget type="math" id="com.github.richbai90.stats.29-undirected-pgms.gibbs" />

An undirected model specifies unnormalized potentials over cliques; the
partition function renormalizes them into probabilities. You may freely
design potentials that encode what configurations you like (the same
freedom that made energy methods natural in physics), and the cost is
immediate: that sum over all configurations is usually the hardest object
in the model. [Lesson 39](/course/stats/mcmc) returns to the same wall
from the sampling side.

<Widget type="quiz" id="com.github.richbai90.stats.29-undirected-pgms.quiz_potentials" />

## The equivalence theorem

<Widget type="math" id="com.github.richbai90.stats.29-undirected-pgms.hc" />

Hammersley–Clifford says the local Markov property, the global separation
property on the graph, and positivity plus a Gibbs factorization are the
same demand stated three ways. The practical content: a Gibbs
distribution over clique potentials *is* the most general positive
distribution respecting the graph. When you write pairwise potentials you
are implicitly claiming nothing bigger than a pair matters, and the
theorem makes that claim precise.

<Widget type="quiz" id="com.github.richbai90.stats.29-undirected-pgms.quiz_separation" />

## An image prior in numbers

Take a row of $N$ pixels with states $\pm 1$ and a pairwise potential
$\exp(J\,x_i x_{k})$ for neighbors, $J > 0$. The potential pays a premium
$\exp(2J)$ for agreement over disagreement, so the most probable images
are the two constant ones, and a typical sample at temperature $1/J$ is a
patchwork whose patch length scales with the correlation length
$\coth J$. This is the Ising model wearing a computer-vision hat, and it
is the cleanest prior for the denoising problem of the assignment set:
measured pixels disagree with their neighbors, the prior says they should
not, and the posterior trades the two demands exactly as
[Lesson 21](/course/stats/tikhonov-nnls) traded smoothness against fit.

<Widget type="stepper" id="com.github.richbai90.stats.29-undirected-pgms.stepper_denoise" />

## What carries forward

Directed models factor into products you can evaluate locally; undirected
models factor into potentials you can design freely but evaluate only
through a partition function. Mixture models in the next lesson are
directed, discrete, and treelike in their latents: the friendliest corner
of the space and the home of expectation maximization.

<Widget type="flashcard" id="com.github.richbai90.stats.29-undirected-pgms.card_gibbs" />

<Widget type="flashcard" id="com.github.richbai90.stats.29-undirected-pgms.card_hc" />
