---
title: Radiometry and Photometry
description: Naming the light an instrument admits — flux, irradiance, radiance, solid angle — the f/2 rule for image brightness, and the human-eye weighting that turns watts into lumens.
order: 16
section: apertures-pupils-instruments
---

Stops and pupils (see [stops, pupils, and windows](13-stops-pupils.md))
decide *how much* light gets through; this lesson names what "how much"
means. Radiometry measures optical energy in physical units — watts and
their geometric derivatives. Photometry is the same geometry re-weighted by
the human eye's spectral response. The two unit systems share every
concept, one-to-one.

## Solid angle

Light from a source spreads over a sphere. The patch of sphere it covers is
measured in **steradians**: a solid angle $\Omega$ subtends an area
$A = R^2\Omega$ on a sphere of radius $R$. A full sphere is $4\pi$ sr; a
cone of half-angle $\theta$ covers

<Widget type="math" id="com.github.richbai90.optics.radiometry.math-solidangle" />

so a small cone has $\Omega \approx \pi\theta^2$ — the $\theta^2$
geometric factor that shadows every result below. The acceptance cone of an
instrument, set by its [aperture stop](13-stops-pupils.md), is exactly such
a cone.

## The radiometric quantities

Four quantities, each a geometric derivative of the last:

<Widget type="math" id="com.github.richbai90.optics.radiometry.math-quantities" />

- **Radiant flux** $\Phi$ (watts): total optical power emitted or received.
- **Irradiance** $E$ (W/m²): flux per unit *area* of a surface — the
  exposure currency of a detector.
- **Radiant intensity** $I$ (W/sr): flux per unit *solid angle* of a point
  source.
- **Radiance** $L$ (W/(sr·m²)): flux per area *and* per solid angle — the
  brightness of a patch as seen from a direction.

One conservation law ties them together and makes radiance special:
**radiance is invariant along a ray** in a lossless system. A pixel's
radiance in the image equals the source patch's radiance — no instrument
can brighten a surface beyond what its radiance allows; it can only gather
more of the sphere around it (larger aperture) or concentrate onto a
smaller image.

<Widget type="quiz" id="com.github.richbai90.optics.radiometry.quiz1" />

## Image brightness: the f/2 rule

The payoff of [stops and pupils](13-stops-pupils.md#numerical-aperture-and-f-number)
is a compact law for how bright a camera's image is. For a scene of
radiance $L$ imaged by a lens of f-number $N = f/\#$, the irradiance on
the focal plane is

<Widget type="math" id="com.github.richbai90.optics.radiometry.math-fnumber" />

Image brightness depends on the *f-number alone* — not on focal length.
That is why exposure dials are labeled f/1.4, f/2, f/2.8, …: each
**stop** multiplies $N$ by $\sqrt{2}$, and since irradiance scales as
$1/N^2$, each stop halves or doubles the light on the sensor. The
$\theta^2$ geometry of the solid angle made this inevitable.

<Widget type="interactive" id="com.github.richbai90.optics.radiometry.int-brightness" />

<Widget type="quiz" id="com.github.richbai90.optics.radiometry.quiz2" />

## Photometry: weighting by the eye

The eye is a terrible watt-meter: it barely registers deep red, peaks near
555 nm (green), and collapses in the dark. Photometry keeps every geometric
unit and replaces watts with **lumens**, weighted by the photopic response
$V(\lambda)$:

<Widget type="math" id="com.github.richbai90.optics.radiometry.math-luminous" />

The pairing is one-to-one: lumen ↔ watt (flux), lux ↔ W/m² (irradiance),
candela ↔ W/sr (intensity), nit ↔ W/(sr·m²) (luminance). The scotopic
response of rod vision shifts the peak toward blue — the Purkinje effect,
why dusk scenes lose red first. For instrument design the lesson is
practical: a detector or an eye cares about the *right-weighted* flux its
[exit pupil](13-stops-pupils.md#entrance-and-exit-pupils) delivers, not
the raw watts.

<Widget type="flashcard" id="com.github.richbai90.optics.radiometry.card-quantities" />

<Widget type="flashcard" id="com.github.richbai90.optics.radiometry.card-stop" />

<Widget type="quiz" id="com.github.richbai90.optics.radiometry.quiz3" />


## Recommended reading and viewing

The quantitative chain is grounded in the lecture-6 notes; the video covers the aperture vocabulary.

<Widget type="resource-link" id="com.github.richbai90.optics.radiometry.link-lecture-6" />

<Widget type="resource-link" id="com.github.richbai90.optics.radiometry.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.radiometry.link-openstax" />

## Assignments

Homework 3 is the instruments capstone: a goldfish in a spherical
waterworld, a ball-lens magnifier, a telephoto design, and a microscope
design — pupils, stops, and magnification everywhere.

<Widget type="resource-link" id="com.github.richbai90.optics.radiometry.link-hw3" />

<Widget type="resource-link" id="com.github.richbai90.optics.radiometry.link-hw3-sol" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 6 — terms: apertures, stops,
  pupils, and windows; single-lens
  camera](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-6-terms-apertures-stops-pupils-and-windows-single-lens-camera/)
  (CC BY-NC-SA 4.0) — the aperture-stop, NA, and f-number grounding
- OpenStax University Physics III, §2.7 (The Camera) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Radiometric and photometric quantities follow the standard SI framework
  (CIE photopic luminous-efficiency function $V(\lambda)$; 683 lm/W at
  555 nm)
