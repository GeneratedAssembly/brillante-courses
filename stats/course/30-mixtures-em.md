---
title: Mixtures and Expectation Maximization
description: Latent class variables, the Gaussian mixture model, responsibilities, the E and M steps, and the K-means limit. After Bishop, chapter 9, and Barber, chapter 10.
order: 30
section: module-4
---

# Mixtures and Expectation Maximization

A histogram with two humps does not come from one Gaussian. It comes from
two Gaussians and a rule for choosing between them, a latent class
variable. The latent class is never observed; it is the reason the
maximum likelihood problem stops having a closed form, and expectation
maximization is the algorithm that lives in that gap. After Bishop,
chapter 9, and Barber, chapter 10.

## The mixture likelihood

<Widget type="math" id="com.github.richbai90.stats.30-mixtures-em.mixture" />

The sum sits inside the logarithm, and that placement is the whole story.
For a single Gaussian the log swallowed the exponential and the maximum
was linear algebra; for the mixture the sum survives, derivatives couple
every parameter to every other, and setting them to zero produces equations
with the unknowns on both sides. The fix is not a cleverer derivative; it
is a better guess about who generated each point.

## Responsibilities

<Widget type="math" id="com.github.richbai90.stats.30-mixtures-em.resp" />

If the class labels were known, each component would fit its own points
and the single-Gaussian formulas would return. The posterior probability
of each label given the data is the soft replacement: the E step computes
responsibilities, the M step refits each component under those weights,
and each component owns exactly the share of each point it can explain.

<Widget type="interactive" id="com.github.richbai90.stats.30-mixtures-em.inter_resp" />

The responsibility is a soft switch: where the components are far apart it
snaps between zero and one, and near the boundary it splits the point.
K-means is the zero-temperature limit of this curve.

<Widget type="stepper" id="com.github.richbai90.stats.30-mixtures-em.stepper_em" />

## Coordinate ascent in disguise

The next lesson proves what this lesson observes: the E step and the M
step each raise a single well-defined objective and never lower the
likelihood. That monotonicity is why EM converges without a step size,
and also why it converges to the *nearest* local optimum: the
initialization you choose for the interactive above is a real modeling
decision, and multi-start is the honest response.

<Widget type="quiz" id="com.github.richbai90.stats.30-mixtures-em.quiz_kmeans" />

## What carries forward

The mixture is the template for every latent-variable model in this
module: a family you could fit if you knew the latents, latents you could
infer if you knew the family, and an alternation between the two. The
Dirichlet version of the same story powers topic models in
[Lesson 32](/course/stats/dirichlet-topics), and the continuous version
becomes the variational autoencoder in
[Lesson 33](/course/stats/continuous-latents).

<Widget type="quiz" id="com.github.richbai90.stats.30-mixtures-em.quiz_em" />

<Widget type="flashcard" id="com.github.richbai90.stats.30-mixtures-em.card_resp" />

<Widget type="flashcard" id="com.github.richbai90.stats.30-mixtures-em.card_em" />

## Teach it back

Responsibilities are the soft switch every latent-variable model in this
module runs on. Teach the E/M alternation before the ELBO lesson
explains why it climbs.

<Widget type="teach" id="com.github.richbai90.stats.30-mixtures-em.teach" />
