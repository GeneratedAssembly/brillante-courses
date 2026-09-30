---
title: Thin Lenses
description: The thin-lens equation, real and virtual images, converging and diverging lenses — and the diopter, the currency every prescription is written in.
order: 9
section: lenses-image-formation
---

A lens is refraction put to work twice: light bends entering the glass and
again leaving it. In the paraxial regime (see
[perfect focusing](07-perfect-focusing-and-the-paraxial-approximation.md)) the
whole action of a lens collapses to a single number, the focal length — and
image formation becomes algebra you can do in your head.

## From two surfaces to one lens

Trace a ray through a lens with the machinery of
[ray transfer matrices](08-ray-transfer-matrices.md): refract at the first
surface, translate through the glass, refract at the second. If the lens is
**thin** — its thickness is negligible compared to the distances involved —
the two surface refractions happen at essentially the same plane, and the
product of three matrices collapses into one:

<Widget type="math" id="com.github.richbai90.optics.thin-lenses.math-lensmaker" />

This is the **lensmaker's equation**. Two consequences are worth pausing on:

- The focal length is a *property of the lens and its environment* — glass
  index $n$ and surface curvatures $R_1, R_2$ — not of the scene in front of
  it. A lens designed for air loses power underwater ($f$ grows), because the
  index contrast that bends the rays shrinks.
- Flipping the lens over swaps $R_1 \leftrightarrow R_2$, and the equation is
  unchanged: a thin lens has the same focal length either way around.

## The thin-lens equation

With the lens reduced to a single plane of power $1/f$, imaging follows from
one propagation, one refraction, one propagation — exactly the stepper
derivation from [ray matrices](08-ray-transfer-matrices.md#reading-images-off-the-matrix):

<Widget type="math" id="com.github.richbai90.optics.thin-lenses.math-thinlens-eq" />

<Widget type="interactive" id="com.github.richbai90.optics.thin-lenses.int-imaging" />

Read the curve: as the object recedes, $s'$ falls toward $f$ (the image
shrinks toward the focal plane); as the object approaches the focal plane,
$s'$ shoots to infinity — an object *at* $f$ sends out collimated light.
For a diverging lens ($f < 0$), $s'$ stays negative at every object distance:
no real image at all.

<Widget type="quiz" id="com.github.richbai90.optics.thin-lenses.quiz1" />

## Real and virtual images

The sign of $s'$ sorts all thin-lens imaging into two families:

- **Real image** ($s' > 0$): rays actually converge on the far side. You can
  catch it on a screen — a camera sensor, a retina, a sheet of paper.
  Formed by a converging lens with $s > f$; always inverted.
- **Virtual image** ($s' < 0$): rays only *appear* to diverge from a point on
  the object side. No screen can catch it, but your eye can — looking back
  through the lens, it sees light coming from that point. Formed by a
  converging lens with $s < f$ (the magnifying glass: upright, enlarged) and
  by *every* diverging lens for a real object (upright, reduced).

<Widget type="quiz" id="com.github.richbai90.optics.thin-lenses.quiz2" />

<Widget type="quiz" id="com.github.richbai90.optics.thin-lenses.quiz3" />

## Sign conventions and diopters

Everything above rides on one compact convention set — the same one the
matrix formalism encodes automatically:

<Widget type="flashcard" id="com.github.richbai90.optics.thin-lenses.card-signs" />

For practice, optometrists never quote focal lengths; they quote **power**,
the reciprocal of $f$ in meters:

<Widget type="flashcard" id="com.github.richbai90.optics.thin-lenses.card-diopter" />

Powers (not focal lengths) add when thin lenses are stacked in contact — the
fact [composite lenses](10-thick-composite.md) build on, and the reason a
prescription can combine sphere, cylinder, and reading add in one number set.

<Widget type="flashcard" id="com.github.richbai90.optics.thin-lenses.card-realvirtual" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.thin-lenses.link-lecture-4" />

<Widget type="resource-link" id="com.github.richbai90.optics.thin-lenses.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 4 — sign conventions, thin
  lenses, real and virtual
  images](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-4-sign-conventions-thin-lenses-real-and-virtual-images/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.5 (Thin Lenses) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
