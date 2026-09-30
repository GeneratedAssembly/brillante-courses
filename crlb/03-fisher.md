---
title: Fisher Information and the CRLB
description: The two forms of Fisher information, why they are equivalent, and the Cauchy–Schwarz derivation of the Cramér–Rao bound.
order: 3
---

The score from the [previous lesson](/course/crlb/score) is a zero-mean
random variable whose size reflects how sharply the log-likelihood peaks.
Now we measure that size and connect it to the best any estimator can do.

## Fisher information

The **Fisher information matrix** is the covariance of the score:

<Widget type="math" id="com.github.richbai90.crlb2.math_fim_cov" />

The second form is often more convenient to compute — differentiate the
score once more and take the negative expectation:

<Widget type="math" id="com.github.richbai90.crlb2.math_fim_hessian" />

<Widget type="math" id="com.github.richbai90.crlb2.math_fim_both" />

## The two forms are the same

The equivalence is not an accident — it is the zero-mean property at work:

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_fim_equivalence" />

Each form earns its keep in a different place:

- the **covariance form** shows up whenever we average squared random
  quantities (the Poisson lesson uses it);
- the **Hessian form** shows up whenever a log-likelihood is easy to
  differentiate twice (the binned point-process lesson uses it).

Later lessons will switch between them freely; now you know the switch is
licensed.

## Curvature is information

The Hessian form has a geometric reading: Fisher information is the
curvature of the expected log-likelihood at the truth. A sharp peak — high
curvature — means small parameter moves cause large score excursions; the
data pins $\theta$ down. A flat likelihood gives near-zero curvature and the
data says almost nothing.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_curvature" />

Notice the exact relationship in the single-parameter Gaussian case:
$I(\mu) = 1/\sigma^2$. Halving the width *quadruples* the information.
The bound below inherits that algebra.

## The Cramér–Rao bound

Now the payoff. For any unbiased estimator, the variance cannot dip below
the reciprocal of the information:

<Widget type="math" id="com.github.richbai90.crlb2.math_crlb_matrix" />

The derivation is one application of Cauchy–Schwarz:

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_crlb" />

Three reading notes:

- the inequality $A \ge B$ between matrices means $A - B$ is **positive
  semidefinite**: every quadratic form $u^{\mathsf T} A u \ge u^{\mathsf T} B u$
  along any direction $u$;
- the bound is *per-distribution*: it assumes the model $p(x;\theta)$ used
  in the derivation matches the data-generating process;
- it is a floor on variance for **unbiased** estimators. Maximum-likelihood
  estimators are asymptotically efficient — they approach the bound as data
  grows — which is why the bound is worth caring about in practice.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_bound_vs_width" />

## Where the course goes

The remainder of the course is a single long exercise in the bookkeeping
this lesson set up: pick a distribution family for real sensor data, compute
its Fisher information, and read the bound. The [Poisson lesson](/course/crlb/poisson)
starts with the simplest non-Gaussian family; the sensor lessons build the
real one.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_fim_forms" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_bound_scope" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_matrix_inequality" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_fim" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_crlb" />