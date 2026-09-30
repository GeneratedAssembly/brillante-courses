---
title: Telescopes
description: A system with zero optical power but nonzero magnifying power — the afocal geometry, angular magnification, and why every large telescope is a mirror.
order: 15
section: apertures-pupils-instruments
---

A microscope looks at something tiny that is *near*. A telescope looks at
something enormous — a star dwarfs the Earth — that is impossibly *far*.
Both are the same architecture, objective plus eyepiece (see
[magnifiers and microscopes](14-magnifiers-microscopes.md)), but the
imaging conditions invert in an instructive way.

## The afocal geometry

Each point of a remote object sends the objective a nearly parallel ray
bundle (anything beyond a few hundred meters is already "at infinity" for
this purpose). The objective focuses its bundle to a real, *demagnified*
image in its back focal plane; the eyepiece — with that image in its front
focal plane — recollimates it. The spacing must satisfy:

<Widget type="math" id="com.github.richbai90.optics.telescopes.math-afocal" />

Zero net power: parallel in, parallel out. The system has no focal length
at all — in matrix language the composite formula of
[lesson 10](10-thick-composite.md) develops $1/F = 0$, and the telescope
matrix has zero in its power entry.

<Widget type="stepper" id="com.github.richbai90.optics.telescopes.stepper-afocal" />

## Angular magnification

A zero-power system can still magnify: what it magnifies is the *angle*
between each incoming ray bundle and the axis. The intermediate image of
height $h$ subtends $h/f_o$ at the objective side and $-h/f_e$ at the
eyepiece side, so:

<Widget type="math" id="com.github.richbai90.optics.telescopes.math-magpower" />

The minus sign is the inversion of the all-positive-lens astronomical
arrangement — unimportant for observing stars, a nuisance for terrestrial
use. The eyepiece is moved along the tube to focus: the intermediate image
plane is fixed by the objective, and its position at the eyepiece's front
focal plane is what the [eyepiece design
points](14-magnifiers-microscopes.md#the-eyepiece) require.

<Widget type="interactive" id="com.github.richbai90.optics.telescopes.int-magpower" />

<Widget type="quiz" id="com.github.richbai90.optics.telescopes.quiz1" />

<Widget type="quiz" id="com.github.richbai90.optics.telescopes.quiz2" />

## Light gathering: why aperture is king

Magnification enlarges; the aperture *gathers*. A distant star is a point
on an essentially uniform sky, and the total light an objective can collect
from it grows with its area:

<Widget type="math" id="com.github.richbai90.optics.telescopes.math-lightgather" />

That is why large telescopes are defined by their aperture: Yerkes, the
largest refractor ever built, carries a 40-inch (1 m) objective in a
62-foot tube — and no larger refractor was ever attempted.

## Reflecting telescopes

Refractors hit three walls at large size: chromatic aberration (the
[achromatic doublet](06-prisms-and-dispersion.md) only softens it), light
absorbed in ever-thicker glass, and lenses that sag under their own
weight. Mirrors hit none of them — reflection is achromatic
([mirrors](12-mirrors.md)), the substrate is supported over its back, and
there is no glass in the light path. Practical consequence:

- **Newtonian**: a parabolic primary plus a flat diagonal mirror folding
  the focus outside the tube.
- **Cassegrain**: a convex secondary reflects light back through a hole in
  the primary — compact tube, and the two mirrors team up to extend the
  effective focal length. Most large telescopes, including the Hubble
  Space Telescope, are Cassegrains.
- **Schmidt (catadioptric)**: the ideal focusing mirror for parallel light
  is a paraboloid; a spherical primary is cheaper but suffers spherical
  aberration, so a weakly figured glass plate at the entrance pupil
  pre-corrects the wavefront. Mirror plus refractor — the
  [catadioptric](12-mirrors.md) family.

<Widget type="flashcard" id="com.github.richbai90.optics.telescopes.card-afocal" />

<Widget type="flashcard" id="com.github.richbai90.optics.telescopes.card-cassegrain" />

<Widget type="quiz" id="com.github.richbai90.optics.telescopes.quiz3" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.telescopes.link-lecture-8" />

<Widget type="resource-link" id="com.github.richbai90.optics.telescopes.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 8 — telescopes; aberrations:
  chromatic, spherical, and
  coma](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-8-telescopes-aberrations-chromatic-spherical-and-coma/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §2.9 (Microscopes and Telescopes) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
