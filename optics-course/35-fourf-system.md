---
title: The 4f System
description: Two lenses make an image by transforming, editing, and un-transforming — the 4f geometry, pupil masks, and Abbe's insight that an image is a sum of its diffraction orders.
order: 35
section: diffraction-fourier-optics
---

[Lesson 8](08-ray-transfer-matrices.md#reading-images-off-the-matrix)
left a promise on the table: a matrix with $C = 0$ images focal plane to
focal plane — "the Fourier-transforming behavior the 4f system
exploits." This lesson cashes it. Two identical lenses, four focal
lengths apart, convert an object to its spectrum, edit the spectrum, and
transform it back into an image.

## The geometry

The train is: object one focal length before lens 1, frequency plane one
focal length after it, lens 2 one focal length after that, image one
focal length after lens 2. Each lens is a transform machine ([the
frequency plane](34-spatial-filtering.md#the-frequency-plane)); the pair
is a transform followed by its inverse:

<Widget type="stepper" id="com.github.richbai90.optics.fourf-system.stepper-walk" />

Two consequences come free. First, the magnification is
$m = -f_2/f_1$ — inverted, and set by the focal-length ratio alone
(the matrix bookkeeping of [composite lenses](10-thick-composite.md#two-lenses-apart-the-composite-formula)
in Fourier clothing). Second, the image is the object **convolved** with
whatever the frequency-plane mask's inverse transform is: masks in the
frequency plane are [spatial filters](34-spatial-filtering.md#what-the-masks-do)
by construction.

<Widget type="quiz" id="com.github.richbai90.optics.fourf-system.quiz1" />

## Binary amplitude and pupil masks

The frequency-plane mask is a pupil in the optical sense ([stops and
pupils](13-stops-pupils.md)) relocated to spectral territory. Binary
amplitude masks are the coarse but instructive cases:

<Widget type="plot" id="com.github.richbai90.optics.fourf-system.plot-masks" />

- **Low-pass disk**: passes the zero and low orders — a sharp-edged
  object images soft, its edges gone (they lived in the high orders).
- **High-pass annulus-dot**: blocks the zero order — a bright object on
  a bright background becomes edges on darkness; uniform regions
  vanish.
- **Annular stop**: passes a band of frequencies — texture of one scale
  survives, everything above and below dies.

The lesson of every demo: the image's *content* is negotiable at the
pupil, and a sharp spectral cutoff convolves the image with the
[transform of that cutoff](32-fraunhofer-fourier.md#apertures-are-fourier-transforms)
— a hard mask rings; a soft one does not.

<Widget type="quiz" id="com.github.richbai90.optics.fourf-system.quiz2" />

## Abbe's view: the image as a sum of orders

Ernst Abbe read the same physics backward, from the microscope. A
periodic object of pitch $p$ diffracts light into orders at
$\sin\theta_m = m\lambda/p$ ([the grating
equation](33-gratings.md#the-grating-equation)); the objective collects
only orders within its numerical aperture. With one order collected,
the image is a uniform patch; with two, fringes at pitch $p$; with many,
a faithful image — the image *is* the sum of its diffraction orders.
The objective's NA therefore caps the spatial frequencies an image can
carry:

<Widget type="math" id="com.github.richbai90.optics.fourf-system.math-abbe" />

An NA = 0.1 objective passes 182 cycles/mm at 550 nm; NA = 0.65 passes
1182. Fine structure beyond that cutoff is not merely degraded — it is
*not in the image at all*, whatever the eyepiece magnifies. This is the
ceiling that [resolution limits](39-resolution-defocus.md) price in
length units, and the reason
[microscope resolution](14-magnifiers-microscopes.md) bowed to
wavelength a dozen lessons ago.

<Widget type="quiz" id="com.github.richbai90.optics.fourf-system.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.fourf-system.card-geometry" />

<Widget type="flashcard" id="com.github.richbai90.optics.fourf-system.card-abbe" />

## Recommended reading and viewing

Lecture 19 builds the 4f system and its binary pupil masks; lecture 20
carries the story to shift invariance.

<Widget type="resource-link" id="com.github.richbai90.optics.fourf-system.link-lecture-19" />

<Widget type="resource-link" id="com.github.richbai90.optics.fourf-system.link-notes" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 19 — the 4F system; binary
  amplitude & pupil
  masks](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-19-the-4f-system-binary-amplitude-pupil-masks/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 19 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec19/)
  (CC BY-NC-SA 4.0)
- Abbe's order-sum picture follows the standard Fourier-optics treatment
  (Goodman, *Introduction to Fourier Optics*)
- Verified numbers: coherent cutoff $\nu = \mathrm{NA}/\lambda$:
  182 cycles/mm (NA 0.1), 1182 (NA 0.65), 2364 (NA 1.3) at λ = 550 nm
