---
title: One Latent-Variable Family
description: PCA, factor analysis, mixtures, LDA, and VAEs as specializations of one generative model; how each choice of likelihood, prior, and constraint recovers a method from Modules 1 through 4. Synthesis lesson.
order: 34
section: module-4
---

# One Latent-Variable Family

Five methods this module treated separately (mixture models, factor
analysis, PPCA, LDA, the VAE) are one model with different settings.
So are the ridge, the LASSO, and Wiener filtering from earlier modules.
This lesson states the shared form once, then walks the dials. The claim
of the whole course is on the line here: there is one estimation lens,
and every forward model is a choice.

## The shared form

<Widget type="math" id="com.github.richbai90.stats.34-unification.master" />

Latents $\mathbf{z}$, a decoder (the forward operator of
[Lesson 1](/course/stats/observation-model)), a prior, and a noise law.
Everything else this module called a "model" is a row in that table. The
dials:

<Widget type="math" id="com.github.richbai90.stats.34-unification.family" />

Read the rows as answers to three questions. What is the latent (a
class label, a code vector, a proportion vector)? What does the decoder
look like (linear with white noise, a table, a network)? And what is the
prior (Dirichlet corners, Gaussian ridges, or nothing at all)? Change
the answers and a different chapter of the literature falls out; keep
them fixed and the inference machinery of
[Lesson 31](/course/stats/em-elbo) is unchanged.

<Widget type="quiz" id="com.github.richbai90.stats.34-unification.quiz_rows" />

## The Module 3 bridge

The bridge from this module back to
[Lesson 19](/course/stats/ill-posedness) and
[Lesson 22](/course/stats/l1-sparsity) runs through the prior dial. A
Gaussian prior on latents, marginalized, turns least squares into ridge;
a Laplace or spike-and-slab prior turns it into the LASSO with its
corners; a Dirichlet prior on proportions produces the constrained
unmixing of [Lesson 24](/course/stats/unmixing). Maximum a posteriori,
[Lesson 7](/course/stats/bayes-map), is the meeting point: the penalty
you added by hand in Module 3 was a log prior all along.

<Widget type="stepper" id="com.github.richbai90.stats.34-unification.stepper_bridge" />

## Choosing by what can break

The dials also price the method. Exact posterior, conjugate update, EM in
closed form: mixtures and factor analysis. Exact prior, intractable
likelihood: MRFs and their partition function. Tractable bound,
approximate posterior: the VAE. Intractable everything, but sampling is
cheap: the Monte Carlo methods of
[Lesson 39](/course/stats/mcmc). The selection is not taste; it follows
from which integral you can do, the same identifiability-first discipline
that opened the course.

<Widget type="quiz" id="com.github.richbai90.stats.34-unification.quiz_select" />

<Widget type="flashcard" id="com.github.richbai90.stats.34-unification.card_dials" />

<Widget type="flashcard" id="com.github.richbai90.stats.34-unification.card_bridge" />

## Teach it back

Module 4's claim — one latent-variable family, many dials — is on the
line here. Teach the shared form and the Module 3 bridge before Module 5
prices the shortcuts.

<Widget type="teach" id="com.github.richbai90.stats.34-unification.teach" />
