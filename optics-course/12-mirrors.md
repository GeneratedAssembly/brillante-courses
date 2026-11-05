---
title: Mirrors
description: Reflection replaces refraction — plane mirrors, spherical concave and convex mirrors, and why big telescopes avoid chromatic aberration entirely.
order: 12
section: lenses-image-formation
---

Everything so far bent light by refraction. Mirrors bend it by
[reflection](05-reflection-and-refraction.md) instead — same ray picture, new
trade-offs, and one decisive advantage: reflection is *achromatic*.

## Why reflect?

A mirror's focusing power does not depend on wavelength at all: the law of
reflection has no index in it, so there is no dispersion and no chromatic
aberration. Glass, by contrast, spreads focus across the spectrum (the
achromatic doublet of [lesson 6](06-prisms-and-dispersion.md) only partially
fixes this). Reflection also lets a big aperture be a single polished surface
supported over its entire back — a lens that large would sag under its own
weight and devour light in its glass. That combination is why every large
modern telescope is a mirror telescope (see
[telescopes](15-telescopes.md)).

## The plane mirror

The zero-power case is worth one careful look. A plane mirror returns an
image that is **virtual** (rays only appear to come from behind the glass),
**upright**, exactly **as far behind the mirror as the object is in front**,
and **mirror-reversed** — the left-right swap you see every morning is a swap
along the viewing axis, not a physical flip. The plane mirror has one
first-order property no lens can match: it is perfectly aberration-free at
every angle, not just paraxially.

## Spherical mirrors: concave and convex

Cut a sphere and polish its inside: a **concave mirror**, converging, with
paraxial focal length $f = R/2$ — the fact you verified qualitatively in
[lesson 7](07-perfect-focusing-and-the-paraxial-approximation.md), where its
marginal-ray failure (spherical aberration) was diagnosed. Its outside: a
**convex mirror**, diverging, $f = -R/2$. Both obey the same Gaussian algebra
as thin lenses:

<Widget type="math" id="com.github.richbai90.optics.mirrors.math-mirroreq" />

The image catalog matches the thin-lens story, with one twist: for a mirror,
a *real* image forms on the **same side** as the object (light bounces back),
while virtual images hide *behind* the mirror.

<Widget type="interactive" id="com.github.richbai90.optics.mirrors.int-magnification" />

<Widget type="quiz" id="com.github.richbai90.optics.mirrors.quiz1" />

<Widget type="quiz" id="com.github.richbai90.optics.mirrors.quiz2" />

## Mirrors in matrix form

Ray tracing through a mirror needs no new matrix either. In the reflection
convention, a spherical mirror multiplies the ray vector exactly like a thin
lens whose power is $2/R$:

<Widget type="math" id="com.github.richbai90.optics.mirrors.math-mirrormatrix" />

So every composite-system tool from [lesson 10](10-thick-composite.md)
applies unchanged to mirror-plus-lens trains — the workhorse geometry of
telescope design, where a mirror primary and lens or mirror secondaries team
up.

<Widget type="quiz" id="com.github.richbai90.optics.mirrors.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.mirrors.card-fR2" />

<Widget type="flashcard" id="com.github.richbai90.optics.mirrors.card-conveximage" />

<Widget type="flashcard" id="com.github.richbai90.optics.mirrors.card-planemirror" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.mirrors.link-lecture-7" />

<Widget type="resource-link" id="com.github.richbai90.optics.mirrors.link-openstax" />

## Assignments

Homework 2 drills the composite-lens and imaging machinery of this section:
a wiper-sensor design built on refraction and total internal reflection,
telescopes at infinite and finite conjugates, and an immersion-lens
derivation.

<Widget type="resource-link" id="com.github.richbai90.optics.mirrors.link-hw2" />

<Widget type="resource-link" id="com.github.richbai90.optics.mirrors.link-hw2-sol" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 7 — basics of mirrors, magnifiers,
  and
  microscopes](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-7-basics-of-mirrors-magnifiers-and-microscopes/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.2 (Images Formed by Plane Mirrors),
  §2.3 (Spherical Mirrors) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
