---
title: The Observation Model
description: The generative equation behind every estimator in this course; forward operator, noise, and the two ways to treat an unknown.
order: 1
section: module-1
---

# The Observation Model

Every inverse problem in this course is one equation. A physical system
with an unknown $\boldsymbol\theta$ produces measurements $\mathbf{y}$
through a known operator $\mathbf{h}$, and noise corrupts the result:

<Widget type="math" id="com.github.richbai90.stats.01-observation.model" />

The forward operator $\mathbf{h}$ encodes the physics: a linear sensor
array has $\mathbf{h}(\boldsymbol\theta) = \mathbf{H}\boldsymbol\theta$; a
photon counter has $y = \lambda T$; a blurred image has convolution with a
point-spread function. The noise $\mathbf{n}$ encodes what you cannot
control: thermal jitter, shot noise, quantization. The statistical
question is the reverse direction: given $\mathbf{y}$, say something
defensible about $\boldsymbol\theta$.

## What kind of thing is the parameter?

The reverse direction depends on what the unknown **is**. The course keeps
two answers side by side:

<Widget type="math" id="com.github.richbai90.stats.01-observation.two_views" />

In the **deterministic** view, $\theta$ is a fixed unknown constant. The
data is random; the parameter is not. "Best" means lowest variance among
estimators that are unbiased, or highest likelihood: the ground of Modules
1 through 3.

In the **Bayesian** view, $\theta$ is a random variable with a prior
$p(\theta)$ that encodes what you knew before the data arrived. "Best"
means lowest average loss over the joint distribution of $\theta$ and
$X$, the ground of the Bayesian lessons and Modules 4 and 5.

The two views are not rivals; they are two scoping decisions. A chip's
temperature coefficient is deterministic during one calibration run and
random across the product line. Choose the view that matches the question
you will be asked tomorrow, not the one that matches your home department.

<Widget type="quiz" id="com.github.richbai90.stats.01-observation.quiz_views" />

## Noise is the whole story

Without noise, estimation is trivial algebra: invert $\mathbf{h}$. Every
hard question in this course lives in the noise term. Its two numbers
decide everything: its **level** relative to the signal, and its
**structure** (independent across samples or correlated across a sensor
array, Gaussian or Poisson, additive or multiplicative).

<Widget type="interactive" id="com.github.richbai90.stats.01-observation.inter_snr" />

The interactive above sweeps the noise level for a single noisy
observation of a parameter near $1$. At low noise the measurement pins the
parameter; at high noise the measurement is mostly noise and any estimator
is guessing. Before Module 1 ends you will be able to state that intuition
as a bound: no estimator can do better than the Cramér–Rao limit set by
the noise.

## Identifiability first

Here is the discipline that separates working estimation from debugging
forever. **Before writing any algorithm, assess how well the data can
constrain the parameters.** Two checks, in order:

1. **Identifiability.** Do distinct parameters produce distinct
   distributions? If $\mathbf{h}(\theta_1)$ and $\mathbf{h}(\theta_2)$
   give the same law for $\mathbf{Y}$, no estimator, however clever, can
   separate them. The failure is structural, not algorithmic.
2. **Precision.** For the noise level you actually have, what is the best
   achievable variance? The Fisher information (Lesson 3) turns the noise
   level into a floor; any estimator you build should be compared against
   it.

<Widget type="math" id="com.github.richbai90.stats.01-observation.identifiability" />

A classic non-identifiable case: two sources of equal spectrum observed
through one sensor. The data depends only on the **sum** of intensities,
so individual intensities are unrecoverable; the map $\theta \mapsto$
distribution is not injective. The fix is more physics (a second sensor,
a different filter), not more statistics.

<Widget type="quiz" id="com.github.richbai90.stats.01-observation.quiz_identifiability" />

## The lesson that follows

With the model in place, the rest of Module 1 assembles the classical
toolkit: unbiasedness and sufficiency (Lesson 2), the Cramér–Rao bound
(Lesson 3), maximum likelihood (Lessons 4–5), and the Bayesian answers
(Lessons 6–7). Every tool answers one question about the model above: how
well, and by what recipe, can $\boldsymbol\theta$ come back out of
$\mathbf{y}$?

<Widget type="flashcard" id="com.github.richbai90.stats.01-observation.card_model" />

<Widget type="flashcard" id="com.github.richbai90.stats.01-observation.card_identifiability" />

## Teach it back

This lesson's equation is the one every later equation in the course
specializes. Lock in the generative model, the two scoping views, and the
identifiability-first discipline before Module 1 continues.

<Widget type="teach" id="com.github.richbai90.stats.01-observation.teach" />
