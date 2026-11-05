---
title: Resolution and Depth of Focus
description: The resolution budget, priced — Rayleigh criteria for every instrument, defocus blur versus the Airy disk, the λ/4 depth-of-focus rule, and the f-stop where aberrations and diffraction swap jobs.
order: 39
section: imaging-systems-resolution
---

"Resolution" is three budgets in one trench coat: diffraction's
wavelength bound, aberrations' design bound, and defocus's focus bound.
This lesson prices each, ties them to the f-number, and cashes the
promises made [at the microscope](14-magnifiers-microscopes.md) and
[at the camera](11-eye-camera.md) a dozen lessons ago.

## The Rayleigh criteria

Two point images are resolved when one's Airy peak falls on the other's
first zero ([the Airy disk](32-fraunhofer-fourier.md#the-circular-aperture-the-airy-disk)):

<Widget type="math" id="com.github.richbai90.optics.resolution-defocus.math-rayleigh" />

The same criterion in microscope clothing, $\delta = 0.61\lambda/\mathrm{NA}$,
resolves the [magnifier lesson's](14-magnifiers-microscopes.md) warning:
an NA 1.4 oil objective at 550 nm resolves $0.24\ \mu\mathrm{m}$ — and
nothing below that, at any magnification. Telescopes: angular
resolution $1.22\lambda/D$ — the eye (5 mm) manages 28 arcseconds, a
50 mm binocular 2.8, an 8 m telescope 0.017 — which the atmosphere
usually triples.

<Widget type="plot" id="com.github.richbai90.optics.resolution-defocus.plot-rayleigh" />

<Widget type="quiz" id="com.github.richbai90.optics.resolution-defocus.quiz1" />

## Defocus: the third budget

Displace the sensor by $\delta z$ from focus and the geometric blur
circle is $b = D\,\delta z/f$ — cone geometry, independent of
wavelength. The diffraction blur is the Airy diameter
$2.44\lambda N$. The crossover between the regimes is a sharp, useful
number:

<Widget type="interactive" id="com.github.richbai90.optics.resolution-defocus.int-defocus" />

A 50 mm lens at f/2.8 crosses at $\delta z \approx \pm 11\ \mu$m —
wide open, focus lives or dies by micrometers; at f/8 the crossover
relaxes to $\pm 86\ \mu$m. The wave-optics version of the same trade is
the λ/4 defocus criterion (a quarter wave of defocus error across the
pupil barely dents the MTF):

<Widget type="math" id="com.github.richbai90.optics.resolution-defocus.math-dof" />

f/8 buys $\pm 70\ \mu$m of depth of focus at 550 nm; f/16 buys
$\pm 282\ \mu$m. The $N^2$ scaling is why depth of field doubles with
each stop, and why macro photography at high magnification starves for
depth.

<Widget type="quiz" id="com.github.richbai90.optics.resolution-defocus.quiz2" />

## The trade: aberration, defocus, diffraction

Stopping down attacks aberrations (spherical and coma fall steeply —
[lesson 17's](20-chromatic-spherical-coma.md#spherical-aberration)
$y^2$, $y^3$ scalings) at the cost of diffraction's $\propto N$
broadening and defocus's $N^2$ depth shrink... read that upside down:
depth *grows* as $N^2$, so the field sharpens while the range widens —
until the Airy disk outgrows the pixel. The **best aperture** sits
where the aberration blur equals the diffraction blur: fast enough that
diffraction does not dominate, slow enough that aberrations have
fallen below it — for good camera lenses, two to three stops down from
wide open. Hyperfocal distance, $H = f^2/(Nc)$ for circle of confusion
$c$, is the same trade with the focus slider: focus at $H$ and
everything from $H/2$ to infinity sits inside the blur budget — 10.4 m
for a 50 mm at f/8 with $c = 30\ \mu$m.

<Widget type="quiz" id="com.github.richbai90.optics.resolution-defocus.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.resolution-defocus.card-rayleigh" />

<Widget type="flashcard" id="com.github.richbai90.optics.resolution-defocus.card-dof" />

## Recommended reading and viewing

Lecture 25 prices resolution and defocus on real systems; OpenStax
§4.6 grounds the criterion in textbook form.

<Widget type="resource-link" id="com.github.richbai90.optics.resolution-defocus.link-lecture-25" />

<Widget type="resource-link" id="com.github.richbai90.optics.resolution-defocus.link-notes" />

<Widget type="resource-link" id="com.github.richbai90.optics.resolution-defocus.link-openstax" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 25 — resolution; defocused
  optical
  systems](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-25-resolution-defocused-optical-systems/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 25 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec25/)
  (CC BY-NC-SA 4.0)
- OpenStax University Physics III, §4.6 (Circular Apertures and
  Resolution) — [book page](https://openstax.org/details/books/university-physics-volume-3) (CC BY 4.0)
- Verified numbers: 1.22λ/D: 27.7 arcsec (5 mm eye), 2.77 (50 mm),
  0.017 (8 m); microscope 0.61λ/NA = 0.24 µm (NA 1.4, 550 nm);
  defocus crossover for a 50 mm lens: ±11 µm (f/2.8), ±86 µm (f/8);
  DOF ±2λN²: ±70 µm (f/8), ±282 µm (f/16); hyperfocal
  f²/(Nc) = 10.4 m (50 mm, f/8, c = 30 µm)
