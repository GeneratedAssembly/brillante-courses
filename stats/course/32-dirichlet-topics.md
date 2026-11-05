---
title: Priors over Proportions
description: The simplex, the Dirichlet distribution, Dirichlet–multinomial conjugacy, predictive probabilities, and LDA. Topic unmixing as the discrete cousin of spectral unmixing. After Bishop, section 2.2, and Barber, chapter 2 and 13.
order: 32
section: module-4
---

# Priors over Proportions

Abundances sum to one. Mixing weights sum to one. Topic proportions sum to
one. Whenever a parameter is a histogram, its natural home is the simplex,
and the natural prior is the Dirichlet, the distribution that puts the
concentration intuition of [Lesson 22](/course/stats/l1-sparsity) to work
on probabilities. After Bishop, section 2.2, and Barber, chapters 2 and 13.

## The Dirichlet

<Widget type="math" id="com.github.richbai90.stats.32-dirichlet-topics.dirichlet" />

The parameters $\boldsymbol\alpha$ do double duty: their sum sets the
concentration (how far from the corners typical draws land) and their
ratios set the mean $\alpha_i / \alpha_0$. With all $\alpha_i = 1$ the
distribution is uniform over the simplex; with $\alpha_i < 1$ mass piles
at the corners, and sparsity appears as a prior belief that most
proportions are near zero.

<Widget type="interactive" id="com.github.richbai90.stats.32-dirichlet-topics.inter_mean" />

## Conjugacy: the multinomial's natural partner

<Widget type="math" id="com.github.richbai90.stats.32-dirichlet-topics.conjugacy" />

Observe multinomial counts, and the Dirichlet returns with its
parameters shifted by the counts, the same add-the-data conjugacy that
made the Gaussian–Gaussian pair of [Lesson 6](/course/stats/bayes-mmse)
so usable. The posterior mean is a concentration-weighted blend of the
prior mean and the empirical frequencies, the predictive probability for the
next draw is exactly that blend, and the posterior mode (when
$\alpha_i > 1$) shifts the empirical frequencies by the prior, Laplace
smoothing with a principled dial.

<Widget type="quiz" id="com.github.richbai90.stats.32-dirichlet-topics.quiz_conjugacy" />

## Latent Dirichlet allocation

A document is a bag of words; the latent structure is a histogram over
topics. LDA gives each document a Dirichlet-drawn topic proportion, draws
a topic per word, and draws the word from that topic's distribution over
the vocabulary. Inference is harder than the conjugate update (the
topics are shared across documents, so the posterior couples everything),
but the machinery is the same coordinate ascent as
[Lesson 31](/course/stats/em-elbo), run over a bigger graph.

<Widget type="stepper" id="com.github.richbai90.stats.32-dirichlet-topics.stepper_lda" />

## The same inverse problem in two languages

Compare LDA with the spectral unmixing of
[Lesson 24](/course/stats/unmixing): a pixel is a simplex-constrained
mixture of endmember spectra; a document is a simplex-constrained mixture
of topic vocabularies. The forward operator changed from spectra to
multinomial probabilities, nonnegativity became the simplex, and Gaussian
noise became multinomial sampling; the estimation problem is untouched.
That is the course thesis in miniature: one estimation lens, many
forward models.

<Widget type="quiz" id="com.github.richbai90.stats.32-dirichlet-topics.quiz_topics" />

<Widget type="flashcard" id="com.github.richbai90.stats.32-dirichlet-topics.card_dirichlet" />

<Widget type="flashcard" id="com.github.richbai90.stats.32-dirichlet-topics.card_conjugacy" />
