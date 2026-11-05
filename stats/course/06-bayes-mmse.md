---
title: "The Bayesian Answer: MMSE"
description: Priors, posteriors, and the conditional-mean estimator; the Gaussian–Gaussian conjugate pair worked to a formula you will reuse for the rest of the course.
order: 6
section: module-1
---

# The Bayesian Answer: MMSE

The Bayesian view re-answers Lesson 1's question. If $\theta$ is a random
variable with prior $p(\theta)$, then data changes what you know about it
through Bayes' rule:

<Widget type="math" id="com.github.richbai90.stats.06-mmse.bayes" />

The posterior $p(\theta \mid x)$ is the complete inference: every
estimator, every confidence statement, every comparison of hypotheses is
a functional of it. The estimator question becomes: which function
$g(x)$ minimizes average loss? For squared error, the answer has a
closed form that needs no calculus of variations:

<Widget type="math" id="com.github.richbai90.stats.06-mmse.mmse" />

**The MMSE estimator is the posterior mean.** Decompose
$\mathbb{E}[(g(X) - \theta)^2]$ into within-slice and between-slice
parts; the within part is $\mathbb{E}[\operatorname{Var}(\theta\mid X)]$,
unavoidable and fixed by the posterior, and the between part is
minimized exactly when $g$ is the conditional mean. Every other
Bayesian estimator in this course is a different loss asking the same
posterior a different question: MAP (Lesson 7) asks for its mode,
credible intervals ask for its quantiles.

## Why priors are not cheating

A prior is a model of where the parameter lives, and it enters with
exactly as much force as the data allows. Weak data cannot override a
sharp prior; strong data washes a vague prior out. The Gaussian–Gaussian
pair makes this quantitative, and its result is the single most reused
formula in Bayesian signal processing.

<Widget type="stepper" id="com.github.richbai90.stats.06-mmse.stepper_gauss" />

<Widget type="math" id="com.github.richbai90.stats.06-mmse.posterior_mean" />

Read the shape: the posterior mean is a **weighted average** of the prior
mean and the data. The weight

<Widget type="math" id="com.github.richbai90.stats.06-mmse.shrinkage" />

is the prior-to-total precision ratio. With a vague prior
($\sigma_0^2 \to \infty$) it vanishes and the answer is the classical
$\bar{x}$. With a sharp prior or one noisy sample it approaches 1 and the
answer is the prior mean. Estimation slides continuously from
"trust the data" to "trust the prior" as the two precisions trade; no
cliff or threshold rule separates the two regimes.

<Widget type="interactive" id="com.github.richbai90.stats.06-mmse.inter_shrink" />

The posterior mean is linear in the data, which is no accident: for
Gaussian models, linear estimation is optimal, and Module 2 (Wiener
filtering, Kalman recursions) is this lesson replayed across time indices.

## The full posterior, not just its mean

The MMSE machinery also delivers uncertainty. The posterior variance is
the harmonic-style combination

<Widget type="math" id="com.github.richbai90.stats.06-mmse.posterior_var" />

The result is always at most the prior variance and at most the data
variance.
Precision (inverse variance) is what combines additively; the Bayesian
update is bookkeeping in precision units. This is the same structure the
Kalman filter will exploit as a recursion, with $\mathbf{C}$ replacing
$\sigma^2$ throughout.

<Widget type="quiz" id="com.github.richbai90.stats.06-mmse.quiz_mmse" />

## Deterministic and Bayesian, finally aligned

Compare the two views on one problem: Gaussian mean, known variance,
$n$ samples. The deterministic CRLB gives $\sigma^2/n$; the Bayesian
posterior variance with a vague prior is $\sigma^2/n$; the frequentist
MSE of $\bar{X}$ is $\sigma^2/n$. Same number, three derivations. The
views differ when data is thin relative to prior knowledge, exactly
where the Bayesian machinery has more to say and where [the problem
sets](/course/stats/assign-1b) will push you.

<Widget type="quiz" id="com.github.richbai90.stats.06-mmse.quiz_compare" />

## Check yourself

<Widget type="flashcard" id="com.github.richbai90.stats.06-mmse.card_mmse" />

<Widget type="flashcard" id="com.github.richbai90.stats.06-mmse.card_precision" />

## Teach it back

The precision-weighted formula above is, by the course's own claim, the
single most reused formula in Bayesian signal processing. Teach the
posterior mean and the precision ledger before Module 1 continues.

<Widget type="teach" id="com.github.richbai90.stats.06-mmse.teach" />
