---
title: "Problem Set 2A: Structural Modeling"
description: Five problems on random processes, rational modeling, the Levinson recursion, Wiener filtering, and spectrum estimation. After Hayes, chapters 3, 4, 5, 7, and 8.
order: 17
section: module-2
---

# Problem Set 2A: Structural Modeling

Five problems on the structural toolkit of Lessons 10–14: describing a
random process, fitting a rational model, running the Toeplitz recursion,
building the optimum linear filter, and estimating a spectrum. Work each
problem before opening its hint; submit; read the reference only after
the verdict. Problems are paraphrased from *Statistical Digital Signal
Processing and Modeling* (Hayes): problem A1 after Hayes, ch. 3 (Yule–Walker
modeling), A2 after Hayes, ch. 5 (Levinson–Durbin), A3 after Hayes, ch. 7
(Wiener filtering), A4 after Hayes, ch. 8 (spectrum estimation), A5 after
Hayes, ch. 4 (rational signal models). All reference solutions are written
fresh for this course and verified numerically.

Conventions: real wide-sense stationary process with autocorrelation
$r_x(k) = E[x(n+k)\,x(n)]$; models follow $x(n) = \sum_{k} a_k x(n-k) +
w(n)$ with $A(z) = 1 - \sum_{k=1}^{p} a_k z^{-k}$; frequencies lie on the
band $-1/2 \le f \le 1/2$.

General facts you may use without re-deriving:

- Yule–Walker: $\mathbf{R}_p\, \mathbf{a} = \mathbf{r}_p$ with
  prediction-error power $\mathcal{E}_p = r_x(0) -
  \mathbf{a}^{\mathsf T}\mathbf{r}_p$.
- Levinson updates: $\Delta_m = r_x(m) - \sum_{i=1}^{m-1} a_{m-1}(i)\,
  r_x(m-i)$, then $k_m = \Delta_m/\mathcal{E}_{m-1}$, $a_m(i) = a_{m-1}(i)
  - k_m\, a_{m-1}(m-i)$, $a_m(m) = k_m$, and $\mathcal{E}_m = (1 -
  k_m^2)\,\mathcal{E}_{m-1}$.
- FIR Wiener: normal equations $\mathbf{R}_y\, \mathbf{c} =
  \mathbf{r}_{yx}$ with error $\mathcal{E} = r_x(0) -
  \mathbf{c}^{\mathsf T}\mathbf{r}_{yx}$.
- Periodogram of white noise of variance $\sigma^2$: expectation
  $\sigma^2$ at every frequency, variance $\sigma^4$ per frequency; a
  $K$-segment average has variance $\sigma^4/K$.

<Widget type="assignment" id="com.github.richbai90.stats.17-assign-2a.a1_yule_walker" />

<Widget type="assignment" id="com.github.richbai90.stats.17-assign-2a.a2_levinson" />

<Widget type="assignment" id="com.github.richbai90.stats.17-assign-2a.a3_wiener_fir" />

<Widget type="assignment" id="com.github.richbai90.stats.17-assign-2a.a4_welch" />

<Widget type="assignment" id="com.github.richbai90.stats.17-assign-2a.a5_factor" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.17-assign-2a.card_chain" />

<Widget type="flashcard" id="com.github.richbai90.stats.17-assign-2a.card_fit" />
