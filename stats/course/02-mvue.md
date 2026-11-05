---
title: Unbiasedness, Sufficiency, and the MVUE
description: What makes an estimator good; unbiasedness, data compression by sufficiency, and the Rao–Blackwell and Lehmann–Scheffé route to the best unbiased estimator.
order: 2
section: module-1
---

# Unbiasedness, Sufficiency, and the MVUE

The deterministic view needs a standard of quality before it can rank
estimators. The classical standard is unbiasedness: on average, the
estimator hits the truth.

## Unbiasedness

An estimator $\hat\theta(X)$ is **unbiased** when its average over data
equals the true parameter:

<Widget type="math" id="com.github.richbai90.stats.02-mvue.unbiased" />

Bias is systematic error. An estimator biased low reads the parameter low
*on average over repeat experiments*, even if any single experiment may
land high. Unbiasedness is not the whole story: a biased estimator with
tiny variance can beat an unbiased one with large variance. It is still
the axis the classical theory organizes around, and the Cramér–Rao bound
of [Lesson 3](/course/stats/crlb) constrains unbiased estimators
specifically.

<Widget type="quiz" id="com.github.richbai90.stats.02-mvue.quiz_bias" />

## Sufficiency: compress without loss

A dataset of $N$ samples carries more numbers than the parameter needs.
A statistic $T(X)$ is **sufficient** for $\theta$ when, once you know
$T$, the raw data adds nothing: the distribution of the data given $T$ no
longer depends on $\theta$. The factorization theorem makes this
checkable without conditional distributions:

<Widget type="math" id="com.github.richbai90.stats.02-mvue.factorization" />

If the likelihood factors into a piece that touches the data only through
$T$ and a piece that does not involve $\theta$ at all, then $T$ is
sufficient. For an i.i.d. Gaussian sample with known variance, the sample
mean $\bar{x}$ is sufficient: no other function of the data knows
anything more about $\theta$. For an i.i.d. sample from a Cauchy
distribution, no low-dimensional statistic is sufficient; the ordered
full sample is, and the problem is genuinely hard.

Sufficiency is lossless compression: every unbiased estimator of $\theta$
can be rebuilt from $T$ alone. The next result makes that precise.

## Rao–Blackwell: condition on the sufficient statistic

Take any unbiased estimator and average it over the sufficient
statistic. The result is better:

<Widget type="stepper" id="com.github.richbai90.stats.02-mvue.stepper_rb" />

<Widget type="math" id="com.github.richbai90.stats.02-mvue.rb_inequality" />

The Rao–Blackwell inequality says conditioning never hurts. Variance
decomposes as "within" plus "between" (the law of total variance), and
conditioning removes the "within" part. Averaging over the conditional
expectation keeps the mean unchanged, so the Rao–Blackwellized estimator
is still unbiased and no worse, usually strictly better.

## Completeness and Lehmann–Scheffé

Rao–Blackwell needs a sufficient statistic to condition on and an
unbiased estimator to start from. The **Lehmann–Scheffé theorem** closes
the loop: if $T$ is a
**complete** sufficient statistic and $g(T)$ is any unbiased estimator,
then $g(T)$ is the unique **minimum-variance unbiased estimator (MVUE)**:
no other unbiased estimator of $\theta$ has smaller variance.

Completeness is the technical hinge: $T$ is complete when no nonzero
function of $T$ has zero expectation for every $\theta$. For exponential
families (Gaussian, Poisson, exponential, Bernoulli) the natural
sufficient statistic is complete, and the route "find $T$, make it
unbiased, done" is a theorem rather than a hope.

<Widget type="math" id="com.github.richbai90.stats.02-mvue.lehmann_scheffe" />

The workflow this buys you, for any i.i.d. model in the exponential
family:

1. Factor the likelihood to find the sufficient statistic $T$.
2. Find *any* unbiased estimator; a crude one will do.
3. Compute $\mathbb{E}[\text{crude} \mid T]$. That conditional
   expectation is the MVUE.

[Problem A2 of the first problem set](/course/stats/assign-1a) walks this
route for the Bernoulli family.

<Widget type="quiz" id="com.github.richbai90.stats.02-mvue.quiz_rb" />

## Check yourself

<Widget type="flashcard" id="com.github.richbai90.stats.02-mvue.card_sufficient" />

<Widget type="flashcard" id="com.github.richbai90.stats.02-mvue.card_rb" />

## Teach it back

The sufficiency–Rao–Blackwell route is the module's classical recipe;
the CRLB lesson and the problem sets assume you own it. Teach the
three-step recipe back before moving on.

<Widget type="teach" id="com.github.richbai90.stats.02-mvue.teach" />
