---
title: About This Course
description: What we cover, how Jev-graded assignments work, the notation we use, and the citation policy.
order: 0
section: start-here
---

# About This Course

Statistical signal processing is one subject that keeps splitting into
departments. Signal processing calls it estimation. Machine learning calls
it inference. Inverse problems call it reconstruction. The mathematics is
one subject: a **forward operator** that maps parameters to measurements, a
**noise mechanism** that corrupts them, and a probabilistic argument that
runs the chain backwards.

This course teaches the chain end to end. A physical system (a photon
counter, a sensor array, a blurred image, a spectral mixture) produces
data through a known operator and unknown parameters. You will learn to
write the generative model, assess how well the data can possibly pin the
parameters down, choose an estimator that respects that limit, and extend
the whole apparatus to priors, latent variables, and sequential dynamics.

## The five modules

1. **Foundations of classical estimation.** The generative equation,
   sufficiency and the minimum-variance unbiased estimator, Cramér–Rao
   bounds, maximum likelihood, and the first Bayesian estimators. This is
   the load-bearing module: every later idea is one of these ideas in new
   clothing.
2. **Structural signal and matrix modeling.** Stationarity, rational
   transfer functions, Toeplitz covariance, Levinson recursion, Wiener
   filters, spectrum estimation, and the Kalman filter. Physics becomes
   matrix structure, and structure becomes algorithms.
3. **Inverse problems, constraints, and regularization.** Discretized
   inversion is ill-posed. Convexity, physical constraints, Tikhonov
   penalties, sparsity, and dictionaries make it estimation again.
4. **Probabilistic graphical models and generative ML.** Latent variables,
   conditional independence, mixtures and EM, the ELBO, Dirichlet models,
   and the factor-analysis line that ends at variational autoencoders.
5. **Information-theoretic inference and dynamics.** Entropy and KL
   divergence, Monte Carlo, MCMC, Hamiltonian Monte Carlo, particle
   filtering, and a decision tree for method selection when closed forms
   fail.

Modules build on each other, but each has its own problem sets, so the
course can also be read module by module.

## How the assignments work

Every module ends with two problem-set lessons. Each problem is an
**assignment widget**: you write a solution in the answer box (markdown
with `$…$` and `$$…$$` math), preview it, and submit.

- **Two engines grade every answer.** A Decisions model (Jev, `typesafe/jev-1.13`)
  compares your answer against the hidden reference and returns a calibrated
  verdict (*correct*, *partially correct*, or *incorrect*) with a score. A
  language model then writes the worked feedback: what is right, what is
  wrong, and the main steps of a correct method, in LaTeX.
- **Hints are opt-in.** Every problem carries a hint you can open before
  submitting. Try without it first; the hint is a nudge, not a solution.
- **The reference unlocks after a graded attempt.** Work the problem, take
  the verdict, and only then compare against the full worked solution.
  Reading the reference first is a waste of a good problem.
- **Equivalent forms count.** A different derivation, a rearranged
  expression, or a cleaner notation is still correct; the grader judges
  mathematics, not phrasing.
- **Drafts save as you type.** Signed-in learners get their graded
  attempts restored on any device; anonymous visitors keep local drafts but
  cannot submit for grading.

You need an account to grade. The preview button works for everyone.

## Notation

These conventions hold across all 45 lessons. Key equations carry
expandable **definition panels** that link back here, so a forgotten symbol
is one click away.

| Symbol | Meaning |
|:--- | :--- |
| $x, \mathbf{x}$ | data: a realization $x$ and the random variable $X$; bold marks vectors over samples or sensors |
| $\theta, \boldsymbol\theta$ | unknown parameter (scalar / vector); deterministic in Modules 1–3, random with a prior $p(\theta)$ in Bayesian settings |
| $\mathbf{y} = \mathbf{h}(\boldsymbol\theta) + \mathbf{n}$ | the master observation model: forward operator $\mathbf{h}$, additive noise $\mathbf{n}$ |
| $p(x;\theta)$ | data distribution at parameter $\theta$; a semicolon separates data from parameter |
| $\ell(\theta) = \ln p(x;\theta)$ | the log-likelihood at the observed data |
| $V(\theta;x) = \nabla_\theta \ell(\theta)$ | the score: the gradient of the log-likelihood at the observed data |
| $\mathbf{I}(\theta)$ | Fisher information matrix |
| $\hat\theta(X)$ | estimator: a function of the data; $\hat\theta$ alone is the realized estimate |
| $\mathbb{E}_X[\cdot]$, $\operatorname{Var}[\cdot]$ | expectation over the data distribution at the true parameter, and variance |
| $\mathcal{N}(\boldsymbol\mu, \mathbf{C})$ | Gaussian with mean $\boldsymbol\mu$ and covariance matrix $\mathbf{C}$ |
| $\mathcal{L}(f)$ | the Laplace transform of $f$, used in Module 2 for rational spectra |
| $\mathcal{H}$, $\mathbf{H}$ | a forward operator (continuous) and its matrix approximation (discrete), Module 3 |
| $q(\cdot)$ | a variational approximation of a posterior, Module 4 |
| $\mathrm{KL}(q \,\|\, p)$ | Kullback–Leibler divergence, Module 5 |

<Widget type="math" id="com.github.richbai90.stats.00-about.master_model" />

Everything in the table is defined the first time it appears in a lesson.
If a later lesson uses a symbol outside this table, its definition panel
says so explicitly.

## Notation in action

One example ties the table together. Photon counting: a source emits at
rate $\lambda$ (the parameter), a detector counts $N$ photons in an
exposure (the data). The model is $N \sim \mathrm{Poisson}(\lambda T)$, the
log-likelihood is $\ell(\lambda) = N\ln(\lambda T) - \lambda T + c$, and
the score is $V = N/\lambda - T$. Lesson 5 of Module 1 turns exactly this
chain into an estimator and its precision bound; Module 3 will make
$\lambda$ a whole spectrum of non-negative rates and Module 5 will sample
its full posterior. The same notation and machinery carry through all
five modules.

## Sources and citation policy

This course is built on classic graduate texts:

- **Kay I**: S. M. Kay, *Fundamentals of Statistical Signal Processing:
  Estimation Theory* (Prentice Hall, 1993).
- **Kay III**: S. M. Kay, *Fundamentals of Statistical Signal Processing:
  Detection Theory* (Prentice Hall, 1998), used for the Monte Carlo
  evaluation of estimators.
- **Hayes**: M. H. Hayes, *Statistical Digital Signal Processing and
  Modeling* (Wiley, 1996).
- **Kailath**: T. Kailath, A. H. Sayed, B. Hassibi, *Linear Estimation*
  (Prentice Hall, 2000).
- **Boyd**: S. Boyd, L. Vandenberghe, *Convex Optimization* (Cambridge
  University Press, 2004).
- **Elad**: M. Elad, *Sparse and Redundant Representations* (Springer,
  2010).
- **Bishop**: C. M. Bishop, *Pattern Recognition and Machine Learning*
  (Springer, 2006).
- **Barber**: D. Barber, *Bayesian Reasoning and Machine Learning*
  (Cambridge University Press, 2012).
- **MacKay**: D. J. C. MacKay, *Information Theory, Inference, and
  Learning Algorithms* (Cambridge University Press, 2003).

The policy that governs every problem and solution in this course:

- Problem statements are **paraphrased, never copied**. They may share
  mathematical content with an exercise in a cited text, with re-chosen
  numbers, but the words are this course's own.
- Sources are cited per problem in the form "after Kay I, §7.6" on each
  assignment lesson.
- **Reference solutions are written fresh** for this course. No solution
  manual is quoted or transcribed.
- No book PDF is served, re-hosted, or embedded anywhere in the course.
  Get the books from a library or the publisher.

The course uses the books as intellectual sources, the way a lecture
course cites its textbook. If you are the rights holder of one of these
works and object to its use here, the acknowledgment below is the contact
point for that conversation.

<Widget type="acknowledge" id="com.github.richbai90.stats.00-about.policy_ack" />

## Where to start

Read the modules in order the first time. Lesson 1 begins with the
observation model, the equation every other equation in the course is a
special case of.

<Widget type="flashcard" id="com.github.richbai90.stats.00-about.card_forward" />

<Widget type="flashcard" id="com.github.richbai90.stats.00-about.card_reference_policy" />

## Teach it back

The master model and this notation are the course's contract: every later
lesson assumes you can read both. Explain them in your own words before
Lesson 1.

<Widget type="teach" id="com.github.richbai90.stats.00-about.teach" />
