---
title: The Evidence Bound
description: Jensen's inequality, the ELBO, the KL gap, and expectation maximization derived as coordinate ascent on a variational objective. After Bishop, chapter 10, and Barber, chapter 11.
order: 31
section: module-4
---

# The Evidence Bound

Lesson 30 ran the E step and the M step and observed that the likelihood
climbed. This lesson explains the climb. There is a single object, a
lower bound on the log likelihood, and the two EM steps are coordinate
ascent on it. The bound, the ELBO, is also the training objective of the
variational autoencoder of [Lesson 33](/course/stats/continuous-latents),
which is why this lesson earns its algebra. After Bishop, chapter 10, and
Barber, chapter 11.

## Jensen and the gap

<Widget type="math" id="com.github.richbai90.stats.31-em-elbo.jensen" />

Concavity moves expectations inside logarithms at a price: the bound is
tight only where the argument is constant. Applied to the log likelihood
of Lesson 30, with the mixture indicator as the latent, the construction
looks like sleight of hand: introduce any distribution $q$ over the
latent, multiply and divide, and read off what was gained:

<Widget type="math" id="com.github.richbai90.stats.31-em-elbo.elbo" />

The identity decomposes the log likelihood into a tractable bound plus an
exactly measured distance. Everything variational (EM, the variational
autoencoder, the posterior approximations of modern Bayesian practice)
is bookkeeping against that one line.

<Widget type="quiz" id="com.github.richbai90.stats.31-em-elbo.quiz_gap" />

## EM as coordinate ascent

<Widget type="stepper" id="com.github.richbai90.stats.31-em-elbo.stepper_derive" />

The E step makes $q$ the exact posterior: it sets the KL gap to zero and
the bound touches the likelihood. The M step then maximizes the expected
complete-data log likelihood over the parameters: a weighted version of
the closed forms from the supervised case. Neither move can lower the
bound, and the E step restores any gap the M step opened, so the
likelihood climbs monotonically to a local optimum.

<Widget type="quiz" id="com.github.richbai90.stats.31-em-elbo.quiz_monotone" />

## Why the gap matters more than the bound

When the exact posterior is tractable (mixtures, factor analysis,
anything conjugate), the ELBO is a proof technique and EM is the
algorithm. When it is not, the gap is the price you pay for a
convenient $q$, and the size of the gap is a modeling decision you make
on purpose. The variational family you choose in
[Lesson 33](/course/stats/continuous-latents) is exactly that decision,
made explicit.

<Widget type="flashcard" id="com.github.richbai90.stats.31-em-elbo.card_elbo" />

<Widget type="flashcard" id="com.github.richbai90.stats.31-em-elbo.card_gap" />

## Teach it back

The ELBO is the single object behind EM, the variational autoencoder,
and the rungs of the final lesson. Teach the bound-plus-gap identity
before moving on.

<Widget type="teach" id="com.github.richbai90.stats.31-em-elbo.teach" />
