---
title: Entropy, KL, and the Cost of a Model
description: Entropy as code length, KL as the price of mismatch, MDL as estimation without a truth, the Occam factor in Bayesian evidence, and Fisher information as curvature. After MacKay, chapters 1, 2, and 28, with a return to Kay I.
order: 37
section: module-5
---

# Entropy, KL, and the Cost of a Model

Module 1 measured estimators; this module measures *beliefs*. The unit
of account is the bit (or the nat, when logs are natural), and every
estimation question of the previous four modules has an information
shadow: how many bits does the data carry, how many does the model
spend, and what does a mismatched belief cost at the receiver. After
MacKay, chapters 1, 2, and 28, closing the loop with the Fisher
information of [Lesson 3](/course/stats/crlb).

## Entropy is code length

<Widget type="math" id="com.github.richbai90.stats.37-entropy-kl.entropy" />

A distribution over outcomes is also a recipe for a code: likely
outcomes get short codewords, and rare ones long ones. The entropy is the
average code length that recipe achieves, and no code beats it. This is
why entropy doubles as surprise: a low-entropy source is predictable,
and a good code says little per symbol.

<Widget type="interactive" id="com.github.richbai90.stats.37-entropy-kl.inter_binary" />

<Widget type="quiz" id="com.github.richbai90.stats.37-entropy-kl.quiz_entropy" />

## KL: the price of the wrong belief

<Widget type="math" id="com.github.richbai90.stats.37-entropy-kl.kl" />

Encode with $q$, live in $p$, and every symbol costs
$H(p) + \mathrm{KL}(p \,\|\, q)$ bits instead of $H(p)$: the
Kullback–Leibler divergence is the exact surcharge for the mismatch.
It is never negative, and it is zero only when $q$ reproduces $p$. The
asymmetry ($\mathrm{KL}(p \,\|\, q)$ never sees regions where $p$ has
no mass, while $\mathrm{KL}(q \,\|\, p)$ is blind in the opposite
direction) is why the direction must be chosen deliberately, and why
variational inference in [Lesson 31](/course/stats/em-elbo) picked the
direction it did.

<Widget type="quiz" id="com.github.richbai90.stats.37-entropy-kl.quiz_kl" />

## Description length: estimation without a truth

<Widget type="stepper" id="com.github.richbai90.stats.37-entropy-kl.stepper_mdl" />

Minimum description length turns this arithmetic into an estimator:
pick the model with the best two-part code, model plus residual. No
true distribution is invoked. The fit term shrinks with every added
parameter; the model term grows, because the receiver must also be told
the parameters to the precision used. Overfitting is a bookkeeping
error, not a moral failing.

<Widget type="quiz" id="com.github.richbai90.stats.37-entropy-kl.quiz_mdl" />

## The Occam factor

<Widget type="math" id="com.github.richbai90.stats.37-entropy-kl.occam" />

Bayesian model comparison pays the same toll through the evidence:
$Z = \int \mathcal{L}(\boldsymbol\theta)\,\pi(\boldsymbol\theta)\,
d\boldsymbol\theta$ is the likelihood averaged under the prior, and a
broad prior dilutes it. The Occam factor makes the penalty exact: the
evidence carries the ratio of posterior volume to prior volume. A model
that spreads its prior where the data never goes pays for the waste,
which is the Bayesian form of the MDL penalty. Problem Set 5A, A2 puts
numbers on a two-prior comparison.

<Widget type="quiz" id="com.github.richbai90.stats.37-entropy-kl.quiz_occam" />

## Fisher information as curvature

<Widget type="math" id="com.github.richbai90.stats.37-entropy-kl.fisher" />

Write the negative log likelihood as an energy and the Fisher
information is its curvature at the optimum: how fast the code length
deteriorates per unit of parameter error. That is [Lesson
3](/course/stats/crlb) read in information units, and it is the same
Hessian that [Lesson 40](/course/stats/hmc) will hand to a
lever. Sensitivity, surprise, and sharpness are one object.

<Widget type="flashcard" id="com.github.richbai90.stats.37-entropy-kl.card_kl" />

<Widget type="flashcard" id="com.github.richbai90.stats.37-entropy-kl.card_occam" />

## Teach it back

KL divergence and the Occam factor are this module's unit of account.
Teach the bit arithmetic — code length, surcharge, two-part code —
before the samplers arrive.

<Widget type="teach" id="com.github.richbai90.stats.37-entropy-kl.teach" />
