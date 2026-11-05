---
title: "Problem Set 5B: Referees and Trackers"
description: Five problems on Monte Carlo evaluation of an estimator, sequential importance sampling, a bootstrap filter run, Gamma–Poisson sequential counting, and choosing the pipeline for a skewed posterior. After Kay, Vol. III, and MacKay.
order: 45
section: module-5
---

# Problem Set 5B: Referees and Trackers

Five problems on Lessons 38 through 43: simulation as the referee for a
Module 1 bound, a weighting step by hand, a full bootstrap-filter run,
sequential photon counting, and the pipeline decision for a posterior
that no Gaussian summary can tell. Work each problem before opening its
hint; submit; read the reference only after the verdict. Problems
are paraphrased from *Fundamentals of Statistical Signal Processing,
Volume III* (Kay, 2013) and *Information Theory, Inference, and
Learning Algorithms* (MacKay, 2003): B1 after Kay III, chapter 11
(Monte Carlo evaluation), B2 and B3 after Kay III, chapter 10 with
Doucet and Johansen, 2011 (sequential Monte Carlo), B4 after Kay III,
chapter 8 with MacKay, chapter 24 (Gamma–Poisson inference), B5 after
MacKay, chapter 28 with the pipeline of [Lesson
43](/course/stats/pipeline-design). All reference solutions are written
fresh for this course and verified numerically.

Conventions: noise variance $1$ and unit weights where unstated; the
particle approximation of a posterior $p(x)$ by weighted particles
$\{x^{(i)}, \bar w_i\}$ is $\hat p(x) = \sum_i \bar w_i
\delta(x - x^{(i)})$; the effective sample size is
$\mathrm{ESS} = 1/\sum_i \bar w_i^2$; a Gamma density with shape $a$
and rate $b$ has mean $a/b$ and mode $(a-1)/b$ for $a > 1$; a
$\Gamma(a, b)$ prior on a Poisson rate with counts $n$ over one
exposure updates to $\Gamma(a + n,\, b + 1)$; a Laplace approximation
is a Gaussian at the posterior mode with variance from the negative
log-density curvature there.

General facts you may use without re-deriving:

- For $N$ i.i.d. Gaussian samples of variance $\sigma^2$, the sample
  mean is efficient: its variance meets the CRLB $\sigma^2/N$.
- Stratified resampling draws particle $k$ whenever a stratum position
  $u_i = (i + 1/2)/M$, $i = 0, \ldots, M-1$, falls inside the
  cumulative weight interval of particle $k$.
- The propagation model of Problems B3: $x' = 0.5x + v$ with $v$ the
  given per-particle innovations.
- $\mathrm{KL}(p \,\|\, q) = \int p(z)\ln(p(z)/q(z))\,dz$; for a
  Gaussian $q$, minimize it numerically or compare moments; both
  routes are accepted with work shown.

<Widget type="assignment" id="com.github.richbai90.stats.45-assign-5b.b1_referee" />

<Widget type="assignment" id="com.github.richbai90.stats.45-assign-5b.b2_sis" />

<Widget type="assignment" id="com.github.richbai90.stats.45-assign-5b.b3_bootstrap" />

<Widget type="assignment" id="com.github.richbai90.stats.45-assign-5b.b4_gamma_poisson" />

<Widget type="assignment" id="com.github.richbai90.stats.45-assign-5b.b5_pipeline" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.45-assign-5b.card_referee" />

<Widget type="flashcard" id="com.github.richbai90.stats.45-assign-5b.card_tracker" />
