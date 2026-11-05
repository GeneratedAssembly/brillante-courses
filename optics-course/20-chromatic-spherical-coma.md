---
title: Chromatic Aberration, Spherical Aberration, and Coma
description: Where the paraxial ideal breaks first — focal length that drifts with wavelength, marginal rays that focus short, and off-axis flares. Abbe numbers, achromatic doublets, and the aperture stop as a design lever.
order: 20
section: aberrations-optical-design
---

The paraxial ideal of [perfect focusing](07-perfect-focusing-and-the-paraxial-approximation.md)
assumes small angles and one wavelength. Real lenses break that ideal in
three independent ways: dispersion makes the focal length a function of
wavelength, finite aperture pulls marginal rays short of the paraxial
focus, and off-axis field points add their own flares. This lesson covers
the first three failures in the classical order — chromatic aberration,
spherical aberration, coma — and the classical fixes. The remaining field
aberrations follow in
[the next lesson](21-astigmatism-field-curvature-distortion.md).

## Chromatic aberration

A thin lens refracts through its index, and the index is a function of
wavelength (see [prisms and dispersion](06-prisms-and-dispersion.md)):

<Widget type="math" id="com.github.richbai90.optics.chromatic-spherical-coma.math-singlet" />

Blue focuses closer than red. The spread of best focus along the axis is
the **longitudinal** chromatic aberration; because the focal length also
scales the image, the image height drifts with wavelength too — the
**lateral** chromatic aberration, visible as color fringes at the edges
of a frame. Both scale roughly as $1/V$, the relative dispersion of the
glass: a crown glass with $V \approx 64$ shifts its focus across the
visible band by about $1.6\%$; a flint with $V \approx 26$ shifts it by
about $4\%$.

<Widget type="interactive" id="com.github.richbai90.optics.chromatic-spherical-coma.int-chromatic" />

<Widget type="quiz" id="com.github.richbai90.optics.chromatic-spherical-coma.quiz1" />

## The achromatic doublet

[Lesson 6](06-prisms-and-dispersion.md) introduced the trick: join a
positive crown element to a negative flint so their chromatic drifts
cancel. The design condition falls out of one line of algebra. Each
element's power is $\varphi_i = (n_i - 1)\kappa_i$, where $\kappa_i$ is
the curvature sum — pure geometry, independent of wavelength. The
achromatizing condition asks the *total* power to stay put as the
wavelength moves between the F (486 nm) and C (656 nm) lines:

<Widget type="stepper" id="com.github.richbai90.optics.chromatic-spherical-coma.stepper-achromat" />

<Widget type="math" id="com.github.richbai90.optics.chromatic-spherical-coma.math-achromat" />

The condition fixes the power split, not the shapes: the designer still
chooses each element's bending to fight the monochromatic aberrations of
this lesson. And the fix is exact only at two wavelengths — between them
a residual **secondary spectrum** remains, typically a few parts in a
thousand of the focal length. Achromats in cameras and telescopes
converge F and C light; violet still strays.

<Widget type="quiz" id="com.github.richbai90.optics.chromatic-spherical-coma.quiz2" />

## Spherical aberration

A spherical surface treats all rays at a given height alike, but a
ray bundle has a spread of heights. Rays through the outer **zone** of a
converging lens bend more than the paraxial rays at its center (their
incidence angles are larger, so the small-angle approximation is worse),
and they cross the axis closer to the lens. The axial gap between
marginal and paraxial focus is the **longitudinal spherical aberration**;
its blur at the paraxial focus is the **transverse** aberration. For a
given lens the longitudinal error grows with the square of the zone
height, the transverse error with its cube — so stopping a lens down
from f/2 to f/4 cuts longitudinal spherical aberration fourfold and
transverse eightfold, while the diffraction spot grows. The best focus
sits between marginal and paraxial, where the blur circle of least
confusion is smallest.

<Widget type="math" id="com.github.richbai90.optics.chromatic-spherical-coma.math-sa" />

Three levers attack it. **Bending**: for a given power, spherical
aberration depends on shape — a biconvex lens used at 1:1 conjugates has
least when the two surface powers are equal; strongly asymmetric uses
want a meniscus bent toward the steep side (the *best-form* lens).
**Stop position**: moving the aperture stop changes which part of each
surface the rays sample. **Splitting**: two shallow lenses do the work
of one deep one, each contributing far less — this is why camera lenses
have many elements.

<Widget type="quiz" id="com.github.richbai90.optics.chromatic-spherical-coma.quiz3" />

## Coma

Tilt the object point off axis and the zones stop nesting. Each annular
zone of the aperture now images the point at a different height *and*
different scale, so the image of a point smears into a comet — a bright
core trailed by a wedge of flare pointing toward or away from the axis,
depending on the sign. Coma is the aberration of the off-axis bundle,
growing with the square of aperture and linearly with field angle.

Coma has a lever spherical aberration lacks: it can be tuned to zero by
shifting the aperture stop along the axis, because the stop selects
which skew rays reach the image. A system corrected for both spherical
aberration and coma is called **aplanatic** — and such point pairs
exist exactly, as
[optical design and GRIN optics](22-optical-design-grin.md#aplanatic-points)
will show. Field astigmatism and curvature take over once the aperture
is cleaned up, which is the order the next lesson follows.

<Widget type="flashcard" id="com.github.richbai90.optics.chromatic-spherical-coma.card-achromat" />

<Widget type="flashcard" id="com.github.richbai90.optics.chromatic-spherical-coma.card-stopping" />

## Recommended reading and viewing

The aberration taxonomy of this lesson is lecture 8's second half and
lecture 9's first half; the OpenStax eye section grounds astigmatism's
most familiar case, developed next lesson.

<Widget type="resource-link" id="com.github.richbai90.optics.chromatic-spherical-coma.link-lecture-8" />

<Widget type="resource-link" id="com.github.richbai90.optics.chromatic-spherical-coma.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.chromatic-spherical-coma.link-lecture-9" />

<Widget type="resource-link" id="com.github.richbai90.optics.chromatic-spherical-coma.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 8 — telescopes; aberrations:
  chromatic, spherical, and
  coma](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-8-telescopes-aberrations-chromatic-spherical-and-coma/)
  (CC BY-NC-SA 4.0) — chromatic aberration and the achromat condition
- MIT OCW 2.71 Optics, Spring 2009, [lecture 9 — more aberrations; optical
  design; GRadient INdex
  (GRIN)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-9-more-aberrations-optical-design-gradient-index-grin/)
  (CC BY-NC-SA 4.0) — spherical aberration and coma in the design context
- OpenStax University Physics III, §2.6 (The Eye) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Abbe numbers and glass data follow the standard Schott catalog values
  used in [lesson 6](06-prisms-and-dispersion.md) ($V_d \approx 64$ for
  N-BK7, $V_d \approx 26$ for N-SF11)
