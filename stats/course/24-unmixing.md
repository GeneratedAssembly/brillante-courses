---
title: Unmixing on the Simplex
description: Spectral unmixing as simplex-constrained least squares; linear mixing, nonnegativity, sum-to-one, fully constrained least squares, and a Dirichlet preview. After Boyd and Vandenberghe chapter 4; the FCLS estimator after Heinz and Chang, 2001.
order: 24
section: module-3
---

# Unmixing on the Simplex

Pixels lie. A hyperspectral pixel over a forest records photons from canopy,
understory, and soil at once; a DOE sensor pixel integrates a whole band of
the spectrum. The observation is a *mixture*, and the estimation problem is
to take mixtures apart. Spectral unmixing, after Heinz and Chang (2001), is
the cleanest physical instance of everything Module 3 has built: a linear
forward model, physical constraints on the geometry of
[Lesson 20](/course/stats/convex-geometry), and a KKT system with
interpretable multipliers.

## The linear mixing model

<Widget type="math" id="com.github.richbai90.stats.24-unmixing.mixing" />

The abundance vector $\mathbf{w}$ lives on the probability simplex
$\Delta^{K-1}$: nothing negative, everything summing to one. That is a
budget of material. The forward matrix $\mathbf{E}$ collects the endmember spectra,
one physical column per material, and the observation is a point in the
cone those columns span.

## Fully constrained least squares

<Widget type="math" id="com.github.richbai90.stats.24-unmixing.fcls" />

Solve the unconstrained least squares first; if it lands inside the
simplex, the constraints were silent. If not, the KKT machinery of
[Lesson 21](/course/stats/tikhonov-nnls) prices the violated bounds and the
solution slides to a face of the simplex. The multipliers inherit physical
meaning: a positive bound multiplier marks a material the data wants to
underweight below zero: a genuine impossibility, not a small correction.

<Widget type="quiz" id="com.github.richbai90.stats.24-unmixing.quiz_mixing" />

## Seeing the mixing in the data

With two endmembers, every feasible pixel is a convex combination, and band
ratios move monotonically along the mixing line. A band ratio is the
cheapest real sensor head: no inversion, one division, and the abundance
reads off the slope:

<Widget type="interactive" id="com.github.richbai90.stats.24-unmixing.inter_ratio" />

<Widget type="quiz" id="com.github.richbai90.stats.24-unmixing.quiz_ratio" />

## The Dirichlet preview

Abundances are fractions, and fractions with uncertainty are random
vectors on the simplex. The natural distribution there is the Dirichlet,
after the Sparse-Land habit of treating coefficients statistically:

<Widget type="math" id="com.github.richbai90.stats.24-unmixing.dirichlet" />

The concentration $\alpha$ plays the role of a prior sample size: large
$\alpha$ means tight certainty around the mean abundances, small $\alpha$
means the mixing proportions themselves are near a corner (nearly pure
pixels). Module 4 develops the full probabilistic machinery for such latent
compositions; this lesson only plants the flag.

## What carries forward

Unmixing closes the deterministic half of the module: constraints from
physics, penalties from priors, geometry to hold them together, and
[Lesson 25](/course/stats/numerics) next asks how all of this is actually
computed, and when to check convexity before trusting any optimizer at
all.

<Widget type="flashcard" id="com.github.richbai90.stats.24-unmixing.card_mixing" />

<Widget type="flashcard" id="com.github.richbai90.stats.24-unmixing.card_dirichlet" />
