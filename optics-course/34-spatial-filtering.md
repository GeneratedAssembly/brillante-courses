---
title: Spatial Filtering and the Frequency Plane
description: A lens's focal plane is the Fourier transform of its input — so masks there act on spatial frequency the way electronic filters act on time. Smoothing, sharpening, and Zernike's phase contrast.
order: 34
section: diffraction-fourier-optics
---

[The far field is a Fourier transform](32-fraunhofer-fourier.md#apertures-are-fourier-transforms)
— and a lens parks the far field one focal length away. Put the two
together and the focal plane of a lens becomes a *spectrum analyzer for
space*: every position in it corresponds to a spatial frequency, and a
mask placed there edits the image the way an equalizer edits sound.

## The frequency plane

For a lens of focal length $f$ with collimated, coherent illumination,
a feature of spatial frequency $\nu$ (cycles per millimeter) in the
object diffracts light to one spot in the back focal plane:

<Widget type="math" id="com.github.richbai90.optics.spatial-filtering.math-frequencyplane" />

Scale check: $f = 100$ mm at 550 nm maps 9.1 cycles/mm to each
millimeter of focal-plane offset — 1 mm off axis is 9.1 cycles/mm, 2 mm
is 18.2. Low frequencies (broad object features) cluster at the axis;
high frequencies (fine detail, edges) fly to the rim. The pupil edge is
a cutoff: light diffracted beyond it never reaches the image, which is
one way to say that the objective's NA bounds the image's detail
([Abbe's view](35-fourf-system.md#abbe-s-view-the-image-as-a-sum-of-orders)).

<Widget type="plot" id="com.github.richbai90.optics.spatial-filtering.plot-transfer" />

<Widget type="quiz" id="com.github.richbai90.optics.spatial-filtering.quiz1" />

## What the masks do

A transparency in the frequency plane multiplies the object's spectrum —
convolution's Fourier dual ([the transform
theorems](32-fraunhofer-fourier.md)):

- **Low-pass** (small clear circle at the axis): keeps slow variations,
  kills edges and fine texture — the image blurs.
- **High-pass** (opaque center dot): removes bulk brightness, keeps
  gradients — the image becomes an edge map.
- **Notch** (dark ring): removes one specific periodicity — a halftone
  screen or a grid vanishes from the image while everything else
  survives.

The pupil itself is a low-pass filter whether or not you admit it: the
clear aperture passes $\nu \le \mathrm{NA}/\lambda$ and stops the rest
(182 cycles/mm at NA = 0.1, λ = 550 nm). Every real image is filtered;
optical design decides *how hard*.

<Widget type="quiz" id="com.github.richbai90.optics.spatial-filtering.quiz2" />

## Phase objects and phase contrast

A living cell in a microscope is, optically, nearly transparent: it
delays light by a phase that depends on thickness and index, and
[detectors record intensity only](24-wave-equation-phasors.md#harmonic-waves-and-phasors)
— so an ideal phase object images as *nothing*. Zernike's 1930s fix is
spatial filtering with surgical precision: the phase structure's
spectrum concentrates at the axis (the zero order), and the phase
*slopes* scatter to the rim. Shift the zero order by a quarter wave
(a small phase mask at the axis), and phase gradients interfere into
intensity — the cell appears, glowing on its own background, with no
stain and no light removed. Phase-contrast microscopy, schlieren
imaging of airflow, and the dark-field of the same idea all run on this
one trick; the phase-shift bookkeeping is
[polarization's](26-polarization-poynting.md#making-circular-light-the-fresnel-rhomb)
same arithmetic in a different plane.

<Widget type="quiz" id="com.github.richbai90.optics.spatial-filtering.quiz3" />

<Widget type="flashcard" id="com.github.richbai90.optics.spatial-filtering.card-frequencyplane" />

<Widget type="flashcard" id="com.github.richbai90.optics.spatial-filtering.card-phasecontrast" />

## Recommended reading and viewing

Lecture 18 develops the frequency plane, the filter menu, and the
coherent transfer language that [imaging systems](36-transfer-functions.md)
will generalize.

<Widget type="resource-link" id="com.github.richbai90.optics.spatial-filtering.link-lecture-18" />

<Widget type="resource-link" id="com.github.richbai90.optics.spatial-filtering.link-notes" />

## Sources

- MIT OCW 2.71 Optics, Spring 2009, [lecture 18 — spatial filtering;
  lens transfer functions &
  transforms](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/lecture-18-spatial-filtering-lens-transfer-functions-transforms/)
  (CC BY-NC-SA 4.0)
- MIT OCW 2.71 Optics, Spring 2009, [lecture 18 notes
  (PDF)](https://ocw.mit.edu/courses/2-71-optics-spring-2009/resources/mit2_71s09_lec18/)
  (CC BY-NC-SA 4.0)
- Zernike's phase-contrast method follows the standard treatment
  (Nobel Prize 1953); the zero-order-shift geometry is as described
- Verified numbers: ν = x/(λf) at f = 100 mm, λ = 550 nm: 9.1 cycles/mm
  per mm of focal-plane offset; pupil cutoff NA/λ: 182 cycles/mm at
  NA = 0.1
