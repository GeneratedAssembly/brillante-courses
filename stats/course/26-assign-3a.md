---
title: "Problem Set 3A: Inverse Problems and Constraints"
description: Five problems on conditioning, Tikhonov regularization, projected-gradient NNLS, and KKT systems on the simplex. After Boyd and Vandenberghe, appendix C and chapters 4, 5, and 6.
order: 26
section: module-3
---

# Problem Set 3A: Inverse Problems and Constraints

Five problems on the deterministic half of Module 3, Lessons 19 through 22:
reading a forward operator through its singular values, regularizing an
ill-conditioned solve, driving a constrained fit by projection, and pricing
constraints with KKT multipliers. Work each problem before opening its hint;
submit; read the reference only after the verdict. Problems are
paraphrased from *Convex Optimization* (Boyd and Vandenberghe, 2004): A1 and
A5 after Boyd, appendix C (numerical linear algebra), A2 after Boyd, ch. 6
(regularized approximation), A3 after Boyd, ch. 4 (constrained least
squares), A4 after Boyd, ch. 5 (KKT conditions). All reference solutions are
written fresh for this course and verified numerically.

Conventions: vectors are columns; the 2-norm is written
$\|\cdot\|_2$; least squares means minimizing $\|\mathbf{A}\mathbf{x} -
\mathbf{b}\|_2^2$; Tikhonov regularization means minimizing
$\|\mathbf{A}\mathbf{x} - \mathbf{b}\|_2^2 + \lambda\|\mathbf{x}\|_2^2$, so
the regularized normal matrix is $\mathbf{A}^{\mathsf T}\mathbf{A} +
\lambda\mathbf{I}$.

General facts you may use without re-deriving:

- Singular value decomposition: $\mathbf{A} = \mathbf{U}\boldsymbol\Sigma
  \mathbf{V}^{\mathsf T}$ with singular values
  $\sigma_1 \ge \sigma_2 \ge \cdots \ge 0$; the condition number is
  $\kappa(\mathbf{A}) = \sigma_1/\sigma_m$ over the $m$ nonzero singular
  values, and relative error obeys
  $\|\delta\mathbf{x}\|/\|\mathbf{x}\| \le \kappa(\mathbf{A})\,
  \|\delta\mathbf{b}\|/\|\mathbf{b}\|$ for consistent systems.
- Tikhonov solution: $\mathbf{x}_\lambda = (\mathbf{A}^{\mathsf T}\mathbf{A}
  + \lambda\mathbf{I})^{-1}\mathbf{A}^{\mathsf T}\mathbf{b}$; in the SVD
  basis each component is scaled by the filter factor
  $\sigma_i^2/(\sigma_i^2 + \lambda)$.
- Projected gradient on a constraint set $\mathcal{C}$:
  $\mathbf{x}_{k+1} = \mathbf{P}_{\mathcal{C}}(\mathbf{x}_k -
  t\nabla f(\mathbf{x}_k))$ with any step $t \le 1/L$, where $L$ bounds the
  largest eigenvalue of the Hessian.
- KKT conditions for $\min \|\mathbf{E}\mathbf{w} - \mathbf{p}\|^2$
  subject to $\mathbf{w} \ge \mathbf{0}$, $\mathbf{1}^{\mathsf T}\mathbf{w}
  = 1$, with Lagrangian $\|\mathbf{E}\mathbf{w} - \mathbf{p}\|^2 +
  \mu(\mathbf{1}^{\mathsf T}\mathbf{w} - 1) - \boldsymbol\nu^{\mathsf T}
  \mathbf{w}$: stationarity $2\mathbf{E}^{\mathsf T}(\mathbf{E}\mathbf{w} -
  \mathbf{p}) + \mu\mathbf{1} - \boldsymbol\nu = \mathbf{0}$, with
  $\boldsymbol\nu \ge \mathbf{0}$ and complementary slackness
  $\nu_i w_i = 0$.

<Widget type="assignment" id="com.github.richbai90.stats.26-assign-3a.a1_conditioning" />

<Widget type="assignment" id="com.github.richbai90.stats.26-assign-3a.a2_filter_factors" />

<Widget type="assignment" id="com.github.richbai90.stats.26-assign-3a.a3_projected_gradient" />

<Widget type="assignment" id="com.github.richbai90.stats.26-assign-3a.a4_kkt_simplex" />

<Widget type="assignment" id="com.github.richbai90.stats.26-assign-3a.a5_pseudoinverse" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.26-assign-3a.card_cond" />

<Widget type="flashcard" id="com.github.richbai90.stats.26-assign-3a.card_price" />
