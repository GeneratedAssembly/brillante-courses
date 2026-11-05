---
title: "Problem Set 3B: Sparsity, Pursuit, and Unmixing"
description: Five problems on soft thresholding and ISTA, OMP, dictionary learning by MOD, fully constrained unmixing, and coherence bounds. After Elad, chapters 2, 3, 6, and 12, and Heinz and Chang 2001.
order: 27
section: module-3
---

# Problem Set 3B: Sparsity, Pursuit, and Unmixing

Five problems on the sparsity half of Module 3: thresholding iterations,
greedy pursuit with and without orthogonalization, one half of the
dictionary-learning loop, a fully constrained unmixing job, and the
coherence arithmetic that says when a sparse answer is the answer. Work each
problem before opening its hint; submit; read the reference only after
the verdict. Problems are paraphrased from *Sparse and Redundant
Representations* (Elad, 2010): B1 after Elad, ch. 6 (iterative shrinkage),
B2 after Elad, ch. 3 (greedy pursuit), B3 after Elad, ch. 12 (dictionary
learning), B5 after Elad, ch. 2 (uniqueness); B4 after Heinz and Chang
(2001), the fully constrained least squares unmixing estimator. All
reference solutions are written fresh for this course and verified
numerically.

Conventions: dictionaries have unit-norm columns unless a problem says
otherwise; sparsity $\|\mathbf{x}\|_0$ counts nonzero entries; the
soft-thresholding operator is
$\mathcal{S}_\lambda(v) = \mathrm{sign}(v)\max(|v| - \lambda, 0)$ applied
entrywise; ISTA for $\min \frac{1}{2}\|\mathbf{D}\mathbf{x} -
\mathbf{b}\|^2 + \lambda\|\mathbf{x}\|_1$ with step size $t \le
1/\lambda_{\max}(\mathbf{D}^{\mathsf T}\mathbf{D})$ is
$\mathbf{x}_{k+1} = \mathcal{S}_{t\lambda}(\mathbf{x}_k -
t\mathbf{D}^{\mathsf T}(\mathbf{D}\mathbf{x}_k - \mathbf{b}))$.

General facts you may use without re-deriving:

- OMP: at each iteration pick the atom maximizing
  $|\mathbf{d}_j^{\mathsf T}\mathbf{r}|$ against the current residual, then
  re-fit all selected atoms jointly by least squares and recompute the
  residual from that fit.
- MOD dictionary update with fixed codes $\mathbf{X}$:
  $\mathbf{D}_{\text{new}} = \mathbf{Y}\mathbf{X}^{\mathsf T}
  (\mathbf{X}\mathbf{X}^{\mathsf T})^{-1}$.
- Uniqueness: if a signal has a representation with
  $\|\mathbf{x}\|_0 < \mathrm{spark}(\mathbf{D})/2$, that representation is
  unique; the computable surrogate guarantees uniqueness whenever
  $\|\mathbf{x}\|_0 < \tfrac{1}{2}(1 + 1/\mu(\mathbf{D}))$, where the
  mutual coherence $\mu(\mathbf{D})$ is the largest absolute inner product
  between distinct unit-norm columns.
- Fully constrained least squares: $\min \|\mathbf{E}\mathbf{w} -
  \mathbf{p}\|^2$ subject to $\mathbf{w} \ge \mathbf{0}$ and
  $\mathbf{1}^{\mathsf T}\mathbf{w} = 1$; KKT as in Problem Set 3A, with
  stationarity $2\mathbf{E}^{\mathsf T}(\mathbf{E}\mathbf{w} - \mathbf{p}) +
  \mu\mathbf{1} - \boldsymbol\nu = \mathbf{0}$.

<Widget type="assignment" id="com.github.richbai90.stats.27-assign-3b.b1_ista" />

<Widget type="assignment" id="com.github.richbai90.stats.27-assign-3b.b2_omp" />

<Widget type="assignment" id="com.github.richbai90.stats.27-assign-3b.b3_mod" />

<Widget type="assignment" id="com.github.richbai90.stats.27-assign-3b.b4_fcls" />

<Widget type="assignment" id="com.github.richbai90.stats.27-assign-3b.b5_coherence" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.27-assign-3b.card_threshold" />

<Widget type="flashcard" id="com.github.richbai90.stats.27-assign-3b.card_pursuit" />
