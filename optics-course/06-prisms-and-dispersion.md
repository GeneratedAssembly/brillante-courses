---
title: Prisms and Dispersion
description: Why a prism splits white light, how rainbows form, and how lens designers fight back with achromatic doublets.
order: 6
section: rays-reflection-refraction
---

Newton's crucial experiment (1666–1672): sunlight through a prism spreads into
a fan of colors that a second prism cannot re-whiten by further refraction.
Color is *in* the light, not created by glass — and it separates because glass
pushes each wavelength by a different amount.

## The prism mechanism

A prism deviates a ray by refraction at each of its two faces. For a prism of
apex angle $\alpha$ and index $n$, the total deviation $D$ (the angle between
the incoming and outgoing ray) in the thin-prism limit becomes especially
simple:

<Widget type="math" id="com.github.richbai90.optics.prisms-and-dispersion.math-deviation" />

Because $n$ rises toward short wavelengths (see
[light in matter](04-light-in-matter.md)), violet is deviated more than red,
and white light fans out into a spectrum. The **dispersive power** of a glass
is captured by a difference of indices at standard wavelengths:

<Widget type="math" id="com.github.richbai90.optics.prisms-and-dispersion.math-abbe" />

<Widget type="plot" id="com.github.richbai90.optics.prisms-and-dispersion.plot-glasses" />

<Widget type="quiz" id="com.github.richbai90.optics.prisms-and-dispersion.quiz1" />

## The rainbow

A raindrop is a tiny prism with round geometry: sunlight enters the front of a
drop, refracts, reflects once off the back, and refracts again on exit. Each
step disperses, so different colors leave the drop at slightly different
angles — about 40° from the antisolar direction for violet and 42° for red.
An observer sees red at the top of the arc because those rays reach the eye
from drops higher in the sky. Two internal reflections give the fainter
secondary bow at ~51° with the color order reversed.

> Light enters a drop of water and is reflected from the back of the drop…
> Since the index of refraction of water varies with wavelength, the light is
> dispersed, and a rainbow is observed. — OpenStax University Physics III,
> §1.6 (<https://openstax.org/details/books/university-physics-volume-3>,
> CC BY 4.0)

<Widget type="quiz" id="com.github.richbai90.optics.prisms-and-dispersion.quiz2" />

## Fighting dispersion: the achromatic doublet

In an imaging system dispersion is a bug, not a feature: each wavelength
focuses at a different distance (**chromatic aberration** — treated fully in
the [aberrations section](17-chromatic-spherical-coma.md)). The
18th-century fix exploits a cancellation: join a positive crown-glass element
(low dispersion) to a negative flint element (high dispersion) so the *powers*
add but the *chromatic errors* subtract. The pair can focus red and blue at
(nearly) the same point while still acting as a converging lens — the
**achromatic doublet**, the workhorse of every camera lens since.

<Widget type="quiz" id="com.github.richbai90.optics.prisms-and-dispersion.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.prisms-and-dispersion.card-deviation" />

<Widget type="flashcard" id="com.github.richbai90.optics.prisms-and-dispersion.card-doublet" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.prisms-and-dispersion.link-lecture-2" />

<Widget type="resource-link" id="com.github.richbai90.optics.prisms-and-dispersion.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 2 — reflection and refraction,
  prisms, waveguides, and
  dispersion](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-2-reflection-and-refraction-prisms-waveguides-and-dispersion/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.6 (Dispersion) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)