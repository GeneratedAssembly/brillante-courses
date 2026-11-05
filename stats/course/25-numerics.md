---
title: Optimization in Practice
description: Gradient descent rates, the Newton step in minimization form, convexity checks before optimizing, and interior-point barriers. After Boyd and Vandenberghe, chapters 9 through 11.
order: 25
section: module-3
---

# Optimization in Practice

Every estimator this module produced arrived as an optimization problem, and
so far each one was solved by inspection or a one-page recursion. Real
problems are solved by iteration, after Boyd and Vandenberghe, chapters 9
through 11. This lesson is the practical manual: how fast first-order
methods move, when the Newton step of [Lesson 4](/course/stats/mle#when-algebra-fails-numerical-mle)
is worth its cost, and why you check convexity *before* running anything,
the habit that separates correct work from confident work.

## First-order descent

<Widget type="math" id="com.github.richbai90.stats.25-numerics.descent" />

The rate is governed by the condition number of the problem: the same
$\kappa$ that ruined inversion in [Lesson 19](/course/stats/ill-posedness)
now slows the descent, because the gradient direction is a good direction
only for the well-scaled coordinates. Preconditioning, momentum (the engine
of FISTA from Lesson 22), and step-size schedules are all attempts to shave
the $\kappa$ off.

## The Newton step, in minimization form

<Widget type="math" id="com.github.richbai90.stats.25-numerics.newton" />

Newton is the MLE algorithm of Lesson 4 turned around for minimization:
same quadratic model, same second-order convergence, same price: forming
and factoring the Hessian. The Newton direction is only trustworthy inside
the region where the quadratic model is honest, hence damped iterations and
line searches. Convex problems welcome Newton: the Hessian is positive
definite everywhere, so the model never lies about direction.

<Widget type="quiz" id="com.github.richbai90.stats.25-numerics.quiz_newton" />

## Check convexity first

<Widget type="math" id="com.github.richbai90.stats.25-numerics.convexcheck" />

The check is cheap and it precedes the run: compute the Hessian, test
positive semidefiniteness on the feasible set, verify that constraints
preserve convexity (intersections of convex sets do; nonlinear rewrites may
not). A stationary point found on a convex problem is the global answer;
found on a nonconvex one, it is a rumor. When the problem is nonconvex but
nearly convex, this audit tells you how much to trust the answer, the
estimation-theory echo of
[Lesson 1](/course/stats/observation-model#identifiability-first).

<Widget type="quiz" id="com.github.richbai90.stats.25-numerics.quiz_convexcheck" />

## Interior-point barriers

Inequality constraints enter smoothly through a barrier that forbids the
boundary:

<Widget type="math" id="com.github.richbai90.stats.25-numerics.barrier" />

As $t$ grows, the barrier solution hugs the true constrained optimum ever
more tightly while Newton handles the smooth combined objective: the
interior-point method that made convex optimization a routinely solvable
technology. The simplex-constrained unmixing of
[Lesson 24](/course/stats/unmixing) is a natural customer: no active-set
bookkeeping, just descent with the boundary priced out of reach.

## What carries forward

Module 3 is complete: the ill-posed inverse was diagnosed by its SVD,
constrained by geometry, tamed by penalties, sparsified, unmixed, and now
computed. The problem sets of [Lesson 26](/course/stats/assign-3a) and
[Lesson 27](/course/stats/assign-3b) drill every one of those mechanics by
hand. Module 4 then turns to latent variables (mixtures, EM, graphical
models, the Dirichlet), where the deterministic penalties of this module
become genuine probabilistic structure.

<Widget type="flashcard" id="com.github.richbai90.stats.25-numerics.card_newton" />

<Widget type="flashcard" id="com.github.richbai90.stats.25-numerics.card_rate" />

## Teach it back

Module 3 is complete. Teach its story end to end — the SVD diagnosis,
the geometry, the penalties, the algorithms — before Module 4 turns the
deterministic penalties into genuine priors.

<Widget type="teach" id="com.github.richbai90.stats.25-numerics.teach" />
