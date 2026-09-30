---
title: Perfect Focusing and the Paraxial Approximation
description: What it takes to focus rays exactly, why spherical surfaces almost manage, and the small-angle approximation that makes lens design tractable.
order: 7
section: rays-reflection-refraction
---

A perfect focusing element maps every ray leaving a point source back to a
single point image. Spherical surfaces — the only surfaces a 17th-century
grinder could polish — fail this test in a small, systematic way, and that
failure (aberration) defines optical design. This lesson sets up both the
ideal and the approximation.

## Perfect focusing is possible — but not with spheres

Fermat's principle says light takes the path of least time; a perfect focus is
a surface for which **every path from object point to image point takes the
same time**. Two exact solutions are worth knowing by name:

- **Paraboloidal reflector**: rays parallel to the axis reflect to a single
  focus. Used in telescopes, satellite dishes, searchlights.
- **Ellipsoidal refractor/reflector**: any ray from one focus of an ellipsoid
  passes through the other after a single reflection (and the refractive
  analog with constant-optical-path surfaces). Used in ring lights and laser
  pump cavities.

<Widget type="quiz" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.quiz1" />

A **spherical mirror** focuses paraxial rays (those running close to the axis)
to $f = R/2$, but marginal rays (hitting near the rim) focus closer —
**spherical aberration**. Aplanatic point pairs of a sphere give two zones
where refraction focuses perfectly; camera designers lean on them (this is
where the aplanatic magnifier comes from).

## The paraxial approximation

Exact ray tracing through spherical surfaces involves $\sin\theta$, which is
why it stayed a job for tables and skill until the 19th century. The
paraxial approximation makes it algebra. For small angles (radians),

<Widget type="math" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.math-paraxial" />

With it, refraction at a spherical surface collapses to a linear map of the
ray, and the whole theory of [thin lenses](09-thin-lenses.md),
[thick lenses](10-thick-composite.md), and
[ray transfer matrices](08-ray-transfer-matrices.md) follows. The error grows
as $\theta^3$ — third order — which is precisely the aberration expansion
covered later: spherical aberration, coma, astigmatism are the third-order
corrections to the paraxial ideal.

How small is small? For $\theta = 10° \approx 0.175\,\text{rad}$, the error in
$\sin\theta \approx \theta$ is about 0.5%. Telescope primaries working at
f/8 or slower sit comfortably inside this regime; a microscope objective at
NA 1.3 does not — which is why microscope design is not paraxial.

<Widget type="interactive" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.int-sintheta" />

<Widget type="quiz" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.quiz2" />

<Widget type="quiz" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.card-paraboloid" />

<Widget type="flashcard" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.card-paraxial" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.link-lecture-3" />

<Widget type="resource-link" id="com.github.richbai90.optics.perfect-focusing-and-the-paraxial-approximation.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 3 — focusing, imaging, and the
  paraxial
  approximation](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-3-focusing-imaging-and-the-paraxial-approximation/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.3 (Spherical Mirrors), §2.4 (Images
  Formed by Refraction) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)