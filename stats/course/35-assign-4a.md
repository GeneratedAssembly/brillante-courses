---
title: "Problem Set 4A: Latent Variables and EM"
description: Five problems on explaining away, one EM iteration for a Gaussian mixture, the K-means limit, Dirichlet–multinomial posteriors, and a Bernoulli mixture. After Bishop, chapters 2, 8, and 9.
order: 35
section: module-4
---

# Problem Set 4A: Latent Variables and EM

Five problems on Lessons 28 through 32: reading dependencies off a
graph, one full EM iteration by hand, the zero-temperature limit of a
mixture, the conjugate update on the simplex, and a binary mixture.
Work each problem before opening its hint; submit; read the
reference only after the verdict. Problems are paraphrased from
*Pattern Recognition and Machine Learning* (Bishop, 2006): A1 after
Bishop, section 8.2 (explaining away), A2 and A3 after Bishop, section
9.2 (mixtures of Gaussians and K-means), A4 after Bishop, section 2.2.1
(the Dirichlet distribution), A5 after Bishop, section 9.4 (mixtures of
Bernoulli distributions). All reference solutions are written fresh for
this course and verified numerically.

Conventions: binary events are written $X = 1$ for the positive outcome;
a Gaussian density is $p(x \mid \mu, \sigma^2) =
\mathcal{N}(x \mid \mu, \sigma^2)$ with unit variance denoted
$\sigma^2 = 1$; mixture weights sum to one; counts are multinomial and
proportions live on the simplex $\sum_i \theta_i = 1$,
$\theta_i \ge 0$.

General facts you may use without re-deriving:

- Bayes: $p(a \mid b) = p(a, b)/p(b)$, and for a partition
  $p(b) = \sum_k p(b \mid c_k)\,p(c_k)$ over exhaustive, disjoint
  causes $c_k$.
- The E step responsibility of component $k$ for point $x_n$:
  $r_{nk} = \pi_k \mathcal{N}(x_n \mid \mu_k, \sigma_k^2) /
  \sum_j \pi_j \mathcal{N}(x_n \mid \mu_j, \sigma_j^2)$.
- The M step updates: $N_k = \sum_n r_{nk}$,
  $\pi_k = N_k/N$, $\mu_k = \sum_n r_{nk} x_n / N_k$,
  $\sigma_k^2 = \sum_n r_{nk} (x_n - \mu_k)^2 / N_k$.
- Dirichlet–multinomial: with prior $\mathrm{Dir}(\boldsymbol\alpha)$
  and counts $\mathbf{n}$, the posterior is
  $\mathrm{Dir}(\boldsymbol\alpha + \mathbf{n})$; posterior mean and
  predictive are $(\boldsymbol\alpha + \mathbf{n}) / \alpha_0'$ with
  $\alpha_0' = \sum_i (\alpha_i + n_i)$.

<Widget type="assignment" id="com.github.richbai90.stats.35-assign-4a.a1_explaining" />

<Widget type="assignment" id="com.github.richbai90.stats.35-assign-4a.a2_gmm_em" />

<Widget type="assignment" id="com.github.richbai90.stats.35-assign-4a.a3_kmeans" />

<Widget type="assignment" id="com.github.richbai90.stats.35-assign-4a.a4_dirichlet" />

<Widget type="assignment" id="com.github.richbai90.stats.35-assign-4a.a5_bernoulli" />

## Before you move on

<Widget type="flashcard" id="com.github.richbai90.stats.35-assign-4a.card_collider" />

<Widget type="flashcard" id="com.github.richbai90.stats.35-assign-4a.card_conjugate" />
