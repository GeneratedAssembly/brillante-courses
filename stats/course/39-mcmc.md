---
title: Markov Chain Monte Carlo
description: Metropolis–Hastings from detailed balance, Gibbs sampling as sequential conditionals, burn-in, autocorrelation, and effective sample size. After MacKay, chapter 29, and Barber, chapter 27.
order: 39
section: module-5
---

# Markov Chain Monte Carlo

Importance sampling needs a proposal you can draw from wholesale.
Markov chain Monte Carlo needs only a kernel that preserves the target:
each step proposes, each acceptance enforces balance, and the chain's
histogram converges to the posterior of [Lesson 7](/course/stats/bayes-map)
no matter how nonlinear it is. After MacKay, chapter 29, and Barber,
chapter 27.

## The Metropolis recipe

<Widget type="math" id="com.github.richbai90.stats.39-mcmc.mh_ratio" />

Propose a move, accept it with the ratio of target densities at the new
and old points. The unknown normalizing constant (the evidence of
[Lesson 37](/course/stats/entropy-kl)) cancels, and that cancellation
is the entire reason MCMC can explore posteriors whose integrals no one
can compute. Detailed balance makes the target stationary; irreducibility
makes it the unique limit.

<Widget type="stepper" id="com.github.richbai90.stats.39-mcmc.stepper_mh" />

<Widget type="quiz" id="com.github.richbai90.stats.39-mcmc.quiz_accept" />

## Gibbs: conditionals as the proposal

<Widget type="math" id="com.github.richbai90.stats.39-mcmc.gibbs" />

When each full conditional is a known density, Gibbs sampling replaces
acceptance with rotation: cycle through the blocks, draw each from its
conditional given the rest. Every draw is accepted, so no moves are
wasted, but the chain is exactly as correlated as the conditional
structure allows, and strongly coupled blocks crawl. Problem Set 5A,
A5 runs the Gaussian pair where one sweep is all the structure there is.

<Widget type="quiz" id="com.github.richbai90.stats.39-mcmc.quiz_gibbs" />

## Burn-in, mixing, and effective samples

<Widget type="math" id="com.github.richbai90.stats.39-mcmc.ess" />

The chain's samples are dependent, so the naive $1/\sqrt{N}$ of
[Lesson 38](/course/stats/monte-carlo) flatters it. Autocorrelation
$\rho_t$ inflates the variance by $1 + 2\sum_t \rho_t$, and the
effective sample size discounts the count accordingly: four thousand
correlated draws can be worth forty honest ones. Discard the burn-in,
watch the trace for sticky plateaus, and report ESS, not $N$.

<Widget type="interactive" id="com.github.richbai90.stats.39-mcmc.inter_ess" />

<Widget type="quiz" id="com.github.richbai90.stats.39-mcmc.quiz_diagnostics" />

<Widget type="flashcard" id="com.github.richbai90.stats.39-mcmc.card_balance" />

<Widget type="flashcard" id="com.github.richbai90.stats.39-mcmc.card_burnin" />

## Teach it back

Detailed balance and the evidence cancellation are why sampling
replaces integration. Teach the Metropolis recipe and the diagnostics
before the pipelines lesson leans on them.

<Widget type="teach" id="com.github.richbai90.stats.39-mcmc.teach" />
