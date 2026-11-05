---
title: "Problem Set 2B: State-Space Estimation"
description: Five problems on the Riccati equation, the Kalman recursion, RTS smoothing, and observability. After Kailath, Sayed and Hassibi, chapters 8–10.
order: 18
section: module-2
---

# Problem Set 2B: State-Space Estimation

Five problems on the state-space toolkit of Lessons 15–16: the
steady-state covariance ledger, the Kalman recursion itself, the smoother
that spends the future, and the structural observability question. Work
each problem before opening its hint; submit; read the reference only
after the verdict. Problems are paraphrased from *Linear Estimation*
(Kailath, Sayed and Hassibi): problem B1 after ch. 9 (the Riccati
recursion), B2 after ch. 9 (the Kalman recursion), B3 after ch. 10
(smoothed estimators), B4 after ch. 8 (state-space structure), B5 after
ch. 8 (state covariance and spectra). All reference solutions are written
fresh for this course and verified numerically.

Conventions: scalar state $x(n+1) = a\, x(n) + u(n)$ with white $u$ of
variance $q$; observation $y(n) = x(n) + v(n)$ with white $v$ of variance
$r$; $P(n \mid m)$ is the error covariance of the estimate of $x(n)$ given
data through time $m$.

General facts you may use without re-deriving:

- Predict: $P(n \mid n-1) = a^2\, P(n-1 \mid n-1) + q$.
- Gain: $K(n) = P(n \mid n-1)/(P(n \mid n-1) + r)$ (scalar case).
- Update: $\hat{x}(n \mid n) = \hat{x}(n \mid n-1) + K(n)(y(n) -
  \hat{x}(n \mid n-1))$, and $P(n \mid n) = (1 - K(n))\, P(n \mid n-1)$.
- RTS: $G(n) = P(n \mid n)\, a\, P(n+1 \mid n)^{-1}$, then
  $\hat{x}(n \mid N) = \hat{x}(n \mid n) + G(n)(\hat{x}(n+1 \mid N) - a\,
  \hat{x}(n \mid n))$ and $P(n \mid N) = P(n \mid n) + G(n)^2(P(n+1 \mid
  N) - P(n+1 \mid n))$.
- Observability matrix $\mathcal{O} = \begin{bmatrix} H \\ HF \\ \vdots \\
  HF^{N-1} \end{bmatrix}$ for an $N$-state system.

<Widget type="assignment" id="com.github.richbai90.stats.18-assign-2b.b1_riccati" />

<Widget type="assignment" id="com.github.richbai90.stats.18-assign-2b.b2_kalman_steps" />

<Widget type="assignment" id="com.github.richbai90.stats.18-assign-2b.b3_rts" />

<Widget type="assignment" id="com.github.richbai90.stats.18-assign-2b.b4_observability" />

<Widget type="assignment" id="com.github.richbai90.stats.18-assign-2b.b5_lyapunov" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.18-assign-2b.card_lineage" />

<Widget type="flashcard" id="com.github.richbai90.stats.18-assign-2b.card_smoothing" />
