---
title: Hamiltonian Monte Carlo
description: Gradients as physics, the Hamiltonian equations, leapfrog integration, and why HMC scales to the high dimensions of inverse problems. After MacKay, chapter 30, and Neal, 2011.
order: 40
section: module-5
---

# Hamiltonian Monte Carlo

Random-walk Metropolis pays for every step in a currency of
rejection: proposals overshoot the typical set, and in high dimension
almost all of them do. Hamiltonian Monte Carlo replaces the random walk
with physics: treat the negative log posterior as a potential energy,
roll a frictionless particle through it, and the proposal travels the
level sets of the posterior instead of tripping over them. After
MacKay, chapter 30, and Neal, 2011.

## The phase-space trick

<Widget type="math" id="com.github.richbai90.stats.40-hmc.hamiltonian" />

Augment the parameter $\mathbf{z}$ with momentum $\mathbf{p}$ and
define $H = U(\mathbf{z}) + \tfrac{1}{2}\mathbf{p}^{\mathsf T}\mathbf{p}$
with $U = -\ln \tilde p(\mathbf{z})$. Hamilton's equations conserve $H$
exactly, so a perfect trajectory never leaves the joint
$\exp(-H)$ distribution. The momentum is drawn fresh each iteration and
marginalized by construction: the auxiliary variable costs nothing at
the end.

<Widget type="quiz" id="com.github.richbai90.stats.40-hmc.quiz_potential" />

## Leapfrog: physics on a budget

<Widget type="stepper" id="com.github.richbai90.stats.40-hmc.stepper_leapfrog" />

A computer cannot integrate Hamilton's equations exactly, so HMC uses
the leapfrog: half a momentum step, a full position step, half a
momentum step, repeated. Leapfrog is time-reversible and volume
preserving, which is exactly what the Metropolis correction of
[Lesson 39](/course/stats/mcmc) needs; the final accept step absorbs
whatever energy the discretization leaked. The acceptance rate
diagnoses the step size before the trace does.

<Widget type="math" id="com.github.richbai90.stats.40-hmc.accept" />

<Widget type="quiz" id="com.github.richbai90.stats.40-hmc.quiz_leapfrog" />

## Why inverse problems love it

The posterior of [Lesson 42](/course/stats/sequential-inference) over a
thousand-pixel image is a thousand-dimensional valley, and its
curvature is the Hessian of the forward operator's log likelihood,
the same geometry [Lesson 19](/course/stats/ill-posedness) priced with
singular values. Random walks take $\mathcal{O}(\kappa^2)$ steps to
cross a valley of condition number $\kappa$; HMC rides the gradient
down the valley walls directly, one $\nabla U$ evaluation per leapfrog
half-step, and each evaluation is one adjoint solve; the machinery
of [Lesson 21](/course/stats/tikhonov-nnls) already computes it.

<Widget type="quiz" id="com.github.richbai90.stats.40-hmc.quiz_scaling" />

<Widget type="flashcard" id="com.github.richbai90.stats.40-hmc.card_energy" />

<Widget type="flashcard" id="com.github.richbai90.stats.40-hmc.card_why" />
