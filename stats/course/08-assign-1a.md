---
title: "Problem Set 1A: Classical Estimation"
description: Five problems on likelihood, sufficiency, and the Cramér–Rao bound. After Kay I, chapters 3, 5, and 7.
order: 8
section: module-1
---

# Problem Set 1A: Classical Estimation

Five problems on the deterministic toolkit: likelihood, sufficiency,
Rao–Blackwell, and the Cramér–Rao bound. Work each problem before opening
its hint; submit; read the reference only after the verdict. Problems
are paraphrased from *Fundamentals of Statistical Signal Processing,
Estimation Theory* (Kay I), chapters 3, 5, and 7: problem A1 after Kay I
§7.2, A2 after Kay I §3.5, A3 after Kay I §3.8, A4 after Kay I §7.6, A5
after Kay I §4.3. All reference solutions are written fresh for this
course and verified numerically.

General facts you may use without re-deriving:

- Sample mean $\bar{x} = \frac{1}{n}\sum_i x_i$; for a Gaussian sample
  with known variance $\sigma^2$, $\operatorname{Var}(\bar{X}) =
  \sigma^2/n$.
- CRLB for a Bernoulli proportion: $p(1-p)/n$.
- CRLB for an exponential rate: $\lambda^2/n$.
- For a Gaussian likelihood with a linear model $\mathbf{y} =
  \mathbf{H}\boldsymbol\theta + \mathbf{n}$, known noise covariance
  $\sigma^2\mathbf{I}$, the MLE solves the normal equations
  $\mathbf{H}^{\mathsf T}\mathbf{H}\boldsymbol\theta =
  \mathbf{H}^{\mathsf T}\mathbf{y}$ with covariance
  $\sigma^2(\mathbf{H}^{\mathsf T}\mathbf{H})^{-1}$.

<Widget type="assignment" id="com.github.richbai90.stats.08-assign-1a.a1_gauss_mean" />

<Widget type="assignment" id="com.github.richbai90.stats.08-assign-1a.a2_bernoulli_rb" />

<Widget type="assignment" id="com.github.richbai90.stats.08-assign-1a.a3_exponential_mle" />

<Widget type="assignment" id="com.github.richbai90.stats.08-assign-1a.a4_gauss_variance" />

<Widget type="assignment" id="com.github.richbai90.stats.08-assign-1a.a5_line_fit" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.08-assign-1a.card_efficiency_check" />

<Widget type="flashcard" id="com.github.richbai90.stats.08-assign-1a.card_rb_recipe" />
