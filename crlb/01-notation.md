---
title: The Notation Toolkit
description: Random variables, expectation, and the parametric distributions every later lesson is built on — the single glossary the whole course references.
order: 1
---

Everything in this course is derived from a handful of probabilistic objects.
This lesson defines them once; every later lesson links back here instead of
redefining notation. If a symbol ever looks unfamiliar, the "Definitions"
panel under any equation will point you back to its first appearance.

## Random variables and their distributions

A **random variable** is a quantity whose value is determined by chance — the
outcome of an experiment we cannot fully predict. Capital letters ($X$, $Y$)
name the variable itself; lowercase letters ($x$, $y$) name a particular
realized value we actually observe.

A distribution assigns probabilities to outcomes. For discrete outcomes we
use a **probability mass function** (PMF) $p(x) = P(X = x)$, which sums to
one; for continuous outcomes a **probability density function** (PDF)
$f(x)$, which integrates to one. We write $p(x)$ generically for either and
call the collection of allowed outcomes the **sample space**
$\mathcal{X}$.

<Widget type="math" id="com.github.richbai90.crlb2.math_normalization" />

## Expectation

The **expectation** of a random variable is its probability-weighted average:
the value you would get by averaging infinitely many independent draws.

<Widget type="math" id="com.github.richbai90.crlb2.math_expectation" />

Expectation is **linear**: for constants $a, b$ and random variables $X, Y$,

$$\mathbb{E}[aX + bY] = a\,\mathbb{E}[X] + b\,\mathbb{E}[Y]$$

no matter how $X$ and $Y$ depend on each other — independence is never
needed for linearity. This fact does quiet work throughout the course: the
zero-mean property of the score and both Fisher-information forms are
expectation manipulations, not distribution arguments.

Two more averages appear constantly. The **variance** of $X$,

<Widget type="math" id="com.github.richbai90.crlb2.math_variance" />

measures the spread of $X$ around its mean, and the **covariance** of two
variables $X, Y$,

<Widget type="math" id="com.github.richbai90.crlb2.math_covariance" />

measures how they co-vary: positive when they move together, negative when
they move oppositely, zero when uncorrelated. For vectors, the covariance
matrix collects all pairwise covariances.

## Parametrized distributions

The objects of estimation are not bare distributions but **families** of
distributions indexed by a parameter. We write

<Widget type="math" id="com.github.richbai90.crlb2.math_parametric" />

to mean: the parameter $\theta$ is a fixed, deterministic knob that
*structures* the distribution of $X$. The semicolon is a deliberate
convention — $\theta$ is not a random variable here. Conditioning on an
observed random variable would be written with a bar, $p(x \mid y)$; a
Bayesian treatment that makes $\theta$ random would be written
$p(x \mid \theta)$, and this course does **not** take that route.

The parameter may be a vector: $\theta \in \mathbb{R}^d$. Gradients
$\nabla_\theta$ and Hessians $\nabla_\theta^2$ act componentwise.

## Likelihood and log-likelihood

The same function $p(x;\theta)$ can be read two ways:

- holding $\theta$ fixed and varying $x$ — a probability/density over data;
- holding observed data $x$ fixed and varying $\theta$ — a **likelihood**
  function $L(\theta; x)$ over parameters.

The likelihood is not a probability distribution over $\theta$; it is a
scoring device for how well a parameter value explains the observed data.
Because likelihoods of long data records shrink to vanishing products, we
almost always work with the **log-likelihood**

<Widget type="math" id="com.github.richbai90.crlb2.math_loglik" />

Logarithms turn products into sums — a likelihood over independent pieces of
data becomes a sum of log-terms — and turn multiplicative parameter effects
into additive ones. Both properties matter for event sensors, whose pixels
generate data independently.

## Notation table

| Symbol | Meaning | First used |
|--------|---------|------------|
| $X, Y$ | random variables (capitals) | this lesson |
| $x, y$ | realized values (lowercase) | this lesson |
| $\mathcal{X}$ | sample space | this lesson |
| $\mathbb{E}[\cdot]$ | expectation | this lesson |
| $\operatorname{Var}$, $\operatorname{Cov}$ | variance, covariance | this lesson |
| $\theta$ | deterministic parameter vector | this lesson |
| $p(x;\theta)$ | parametric distribution | this lesson |
| $L(\theta;x)$, $\ell(\theta;x)$ | likelihood, log-likelihood | this lesson |
| $\nabla_\theta$, $\nabla_\theta^2$ | gradient, Hessian w.r.t. $\theta$ | this lesson |
| $a \ge B$ | matrix inequality: $A-B$ positive semidefinite | Fisher lesson |

## Check yourself

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_semicolon" />

<Widget type="quiz" id="com.github.richbai90.crlb2.quiz_linearity" />

## Recall the vocabulary

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_likelihood" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_expectation" />

<Widget type="flashcard" id="com.github.richbai90.crlb2.card_parametric" />

## Next

With the toolkit in hand, the [score lesson](/course/crlb/score) defines the
one function that all of Fisher information theory revolves around: how fast
the log-likelihood moves when the parameter moves.