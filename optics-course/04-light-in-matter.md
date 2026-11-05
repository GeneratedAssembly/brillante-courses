---
title: Light in Matter
description: The index of refraction, why it depends on wavelength (dispersion), and what absorption and scattering do to a beam.
order: 4
section: nature-of-light
---

When light enters matter, three things compete for it: **transmission**
(propagation, but slower), **absorption** (the energy is taken up), and
**scattering** (the direction is randomized). The balance determines whether a
medium is a lens, a filter, or fog.

## The index of refraction

The **index of refraction** $n$ of a medium is the ratio of the speed of light
in vacuum to the speed in the medium:

<Widget type="math" id="com.github.richbai90.optics.light-in-matter.math-index" />

Typical values: air $n \approx 1.0003$, water $n \approx 1.33$, crown glass
$n \approx 1.52$, diamond $n \approx 2.42$. The physical origin is
microscopic: the medium's bound charges are driven by the passing
electromagnetic wave and re-radiate a field that lags the drive, so the net
wave advances more slowly. The stronger the driving response (the closer to an
absorption resonance), the slower the wave — which brings us to the key
point:

## Dispersion: $n$ depends on wavelength

Because the medium's response depends on how far the light frequency sits from
its internal resonances, **$n$ is a function of wavelength**, $n(\lambda)$. In
transparent regions the response strengthens toward shorter wavelengths, so
*n* rises from red to violet. A simple empirical model used throughout lens
design is the **Cauchy equation**:

<Widget type="math" id="com.github.richbai90.optics.light-in-matter.math-cauchy" />

<Widget type="interactive" id="com.github.richbai90.optics.light-in-matter.int-cauchy" />

<Widget type="plot" id="com.github.richbai90.optics.light-in-matter.plot-nlambda" />

Dispersion has two faces. In a prism it *separates* colors (next section); in
an imaging system or a fiber it *smears* them — pulses spread in time, images
acquire colored fringes (chromatic aberration, covered in the aberrations
section).

> Dispersion may produce beautiful rainbows, but it can cause problems in
> optical systems. White light used to transmit messages in a fiber is
> dispersed, spreading out in time and eventually overlapping with other
> messages. — OpenStax University Physics III, §1.6
> (<https://openstax.org/details/books/university-physics-volume-3>, CC BY 4.0)

<Widget type="quiz" id="com.github.richbai90.optics.light-in-matter.quiz1" />

## Absorption and scattering

- **Absorption**: energy is transferred to the medium (electronic transitions,
  lattice vibrations). It is strongly wavelength-dependent — glass is clear in
  the visible but opaque in the infrared and ultraviolet; that is why ordinary
  glass makes a good heat trap and a poor UV optic.
- **Scattering**: redirects light without absorbing it. For particles much
  smaller than the wavelength (air molecules), **Rayleigh scattering** scales
  as $1/\lambda^4$: blue light (450 nm) scatters about
  $(650/450)^4 \approx 4.4$ times more strongly than red light (650 nm). That
  ratio is why the daytime sky is blue — scattered sunlight — and sunsets are
  red — the blue removed along a long atmospheric path.

The slider makes the $1/\lambda^4$ law tangible: sweep the wavelength and
watch the scattering ratio against deep-red light change.

<Widget type="quiz" id="com.github.richbai90.optics.light-in-matter.quiz2" />

<Widget type="slider" id="com.github.richbai90.optics.light-in-matter.slider-rayleigh" />

<Widget type="flashcard" id="com.github.richbai90.optics.light-in-matter.card-n" />

<Widget type="flashcard" id="com.github.richbai90.optics.light-in-matter.card-rayleigh" />


## Recommended reading and viewing

<Widget type="resource-link" id="com.github.richbai90.optics.light-in-matter.link-lecture-2" />

<Widget type="resource-link" id="com.github.richbai90.optics.light-in-matter.link-openstax" />

## Assignments

MIT's first problem set opens with the energy argument that forces a
spherical wave to decay as $1/r$, and spends a full problem on radiometric
order-of-magnitude estimation — both direct practice for this lesson.

<Widget type="resource-link" id="com.github.richbai90.optics.light-in-matter.link-hw1" />

<Widget type="resource-link" id="com.github.richbai90.optics.light-in-matter.link-hw1-sol" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 1 — course organization;
  introduction to optics](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-1-course-organization-introduction-to-optics/)
  and [lecture 2 — reflection and refraction, prisms, waveguides, and
  dispersion](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-2-reflection-and-refraction-prisms-waveguides-and-dispersion/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §1.6 (Dispersion) —
  [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)