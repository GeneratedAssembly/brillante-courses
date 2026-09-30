---
title: Estimation and the Score
description: Estimators, unbiasedness, and the score function — the gradient of the log-likelihood and the reason information exists at all.
order: 2
---

We now have distributions and a way to score parameter values against data.
The statistical question follows immediately: given data drawn from
$p(x;\theta)$, how well can anyone recover $\theta$?

## Estimators

An **estimator** is a recipe that turns data into a parameter guess:

<Widget type="math" id="com.github.richbai90.crlb2.math_estimator" />

The estimator is a random variable — new data $\hat\theta(X)$ produces a new
guess — and so it has a distribution, a mean, and a variance. An estimator
is **unbiased** when its average guess equals the truth:

<Widget type="math" id="com.github.richbai90.crlb2.math_unbiased" />

Bias is systematic error: an estimator biased low reads $\theta$ low *on
average*, no matter how much data arrives. The bound we will derive in the
[on the Fisher lesson](/course/crlb/fisher) constrains **unbiased**
estimators; biased ones can cheat below it by trading variance for error.

## The score function

How does the distribution respond when the parameter moves? The
log-likelihood $\ell(\theta;x)$ records how well $\theta$ explains the
observed $x$; its gradient records the direction of improvement:

<Widget type="math" id="com.github.richbai90.crlb2.math_score" />

This is the **score function** — for a single parameter, simply
$V(\theta;x) = \frac{\partial}{\partial \theta}\ln p(x;\theta)$, the slope
of the log-likelihood at the observed data. Three intuitions:

- a large positive score means "slightly larger $\theta$ explains this data
  noticeably better";
- the score is evaluated *at the observed data* — it is a function of the
  random outcome, hence itself a random variable;
- the score vanishes at the peak of the likelihood: the maximum-likelihood
  estimate is exactly where $V(\theta;x) = 0$.

<Widget type="interactive" id="com.github.richbai90.crlb2.inter_score_gaussian" />

## The zero-mean property

Here is the fact that quietly powers everything that follows. Take the
expectation of the score over the data distribution *at the true
parameter*:

<Widget type="stepper" id="com.github.richbai90.crlb2.stepper_zero_mean" />

The expected score is identically zero:

<Widget type="math" id="com.github.richbai90.crlb2.math_zero_mean" />

Read that carefully: at the true parameter, the data is — on average —
neither evidence for nor against $\theta$. Up the slope of the likelihood,
random outcomes push the score positive; down the slope, negative; the
average is exactly zero *because the distribution itself integrates to one
at every $\theta$*. The zero-mean property needs only linearity of
expectation and differentiability under the integral sign — regularity
conditions, not independence of anything.

## Why this matters

The score is the random variable whose spread *is* information. If the
log-likelihood is steep around the truth, typical data produces large score
values; the estimator can read the gradient reliably and the parameter is
pinned down. If the log-likelihood is flat, the score is small noise and
$\theta$ is hard to recover. The next lesson makes this precise: the
variance of the score, expected over data, is the **Fisher information**.

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_score_meaning" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_zero_mean" />

## Recall

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_score" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_unbiased" />