---
title: The Geometry of Feasibility
description: Convex sets and cones, the nonnegative orthant and the simplex, norm balls as penalty geometry, and projections. After Boyd and Vandenberghe, chapters 2 and 3.
order: 20
section: module-3
---

# The Geometry of Feasibility

Lesson 19 located the failure of inversion in small singular values. The cure
will be to restrict where the estimate may live (nonnegative intensities,
energy-conserving weights, sparse coefficient vectors), and optimization
needs a language for restrictions. That language is convex geometry, after
Boyd and Vandenberghe, chapters 2 and 3. The payoff is practical: on convex
feasible sets, every local minimum is global, and the geometry of the
constraint tells you which algorithm will solve the problem and at what
price.

## Convex sets

<Widget type="math" id="com.github.richbai90.stats.20-convex-geometry.convexdef" />

The definition is a statement about line segments: take any two members, and
the whole segment between them stays inside. Physical constraints are
typically convex, and that is not an accident: feasibility regions carved by
linear conservation laws (energy, mass, probability) are intersections of
half-spaces, and half-spaces are convex.

<Widget type="quiz" id="com.github.richbai90.stats.20-convex-geometry.quiz_convex" />

## The two workhorses: orthant and simplex

<Widget type="math" id="com.github.richbai90.stats.20-convex-geometry.cones" />

The nonnegative orthant $\mathbb{R}_{+}^{N}$ houses every physically
bounded-below quantity: intensities, concentrations, powers. The probability
simplex $\Delta^{K-1}$ houses every allocation of a unit budget: mixing
weights, class posteriors, the spectra that [Lesson 24](/course/stats/unmixing)
will unmix. They interlock: the simplex is the orthant sliced by the
hyperplane $\mathbf{1}^{\mathsf T}\mathbf{w} = 1$.

## Norm balls are penalty geometry

<Widget type="math" id="com.github.richbai90.stats.20-convex-geometry.normballs" />

A penalty term in an objective is a constraint in disguise, and its shape is
the shape of a norm ball. The Euclidean ball is round: it pushes uniformly.
The $\ell_1$ ball is a diamond with corners on the axes: it pushes estimates
toward those corners, which are exactly the sparse points. This one picture
is the entire reason [Lesson 22](/course/stats/l1-sparsity) exists.

## Projections

<Widget type="math" id="com.github.richbai90.stats.20-convex-geometry.projection" />

The projection operator $\mathbf{P}_{\mathcal{C}}$ takes any point and hands
back the closest feasible one. It is the workhorse of constrained algorithms:
take a gradient step, then project, and you never leave the feasible set.
For the orthant the projection clips negatives to zero; for the simplex it
sorts, shifts, and clips, an algorithm cheap enough to run at every
iteration.

<Widget type="quiz" id="com.github.richbai90.stats.20-convex-geometry.quiz_proj" />

## What carries forward

Feasibility is now a first-class design variable: you can state what the
physics demands, and geometry guarantees the optimization stays honest.
[Lesson 21](/course/stats/tikhonov-nnls) puts penalties and constraints
together into solvers, starting with the ridge penalty that
[Lesson 7](/course/stats/bayes-map#the-coincidence-that-opens-module-3)
foreshadowed.

<Widget type="flashcard" id="com.github.richbai90.stats.20-convex-geometry.card_convex" />

<Widget type="flashcard" id="com.github.richbai90.stats.20-convex-geometry.card_normballs" />

## Teach it back

The geometry below is the language Lessons 21 through 25 speak. Teach
convexity, the two workhorses, and the norm balls before the solvers
arrive.

<Widget type="teach" id="com.github.richbai90.stats.20-convex-geometry.teach" />
